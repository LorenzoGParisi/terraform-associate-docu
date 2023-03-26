# TERRAFORM PROVISIONERS

You must use provisioners only if there is no other option.

- Expressions in provisioner blocks cannot refer to their parent resource by name. Instead, they can use the special SELF object.

- Provisioners are only run during creation, not during updating or any other lifecycle. If a creation-time provisioner fails, the resource is marked as tainted. But if you use when = destroy then it happens when the resource get destroyed.

- By default, provisioners that fail will also cause the Terraform apply itself to fail. 

**file**

The file provisioner copies files or directories from the machine running Terraform to the newly created resource. The file provisioner supports both ssh and winrm type connections.
```
resource "aws_instance" "web" {
  # ...

  provisioner "file" {
    source      = "script.sh"
    destination = "/tmp/script.sh"
  }

  provisioner "remote-exec" {
    inline = [
      "chmod +x /tmp/script.sh",
      "/tmp/script.sh args",
    ]
  }
  connection {
    type     = "ssh"
    host     = self.public_ip
    user     = "ubuntu"
    private_key = file("~/.ssh/mykey.pem")
    timeout  = "2m"
  }
}
```

```
resource "local_file" "example" {
  content  = "Hello, world!"
  destination = "/tmp/ciao.txt" 
}
```
**local_exec**

The local-exec invokes a command in the machine that is running terraform after the resource in which is declared is created.
```
resource "null_resource" "example" {
  provisioner "local-exec" {
    command = "echo 'Hello, world!'"
    interpreter = ["/bin/bash", "-c"]
    working_dir = "/tmp"

    when = destroy
  }
}
```
**remote_exec**

The remote-exec provisioner invokes a script on a remote resource after it is created.

The remote-exec provisioner requires a connection and supports both ssh and winrm.

When using the ssh connection type the destination directory must already exist. 
If you need to create it, use a remote-exec provisioner just prior to the file provisioner in order to create the directory

When using the winrm connection type the destination directory will be created for you if it doesn't already exist.
```
resource "aws_instance" "example" {
  ami           = "ami-0c55b159cbfafe1f0"
  instance_type = "t2.micro"

  provisioner "remote-exec" {
    inline = [
      "sudo apt-get update",
      "sudo apt-get install -y nginx",
      "sudo systemctl start nginx",
      "sudo systemctl enable nginx",
    ]
    connection {
      type     = "ssh"
      host     = self.public_ip
      user     = "ubuntu"
      private_key = file("~/.ssh/mykey.pem")
      timeout  = "2m"
    }
    script = "scripts/setup.sh"

  }
}
```

winRM
```
# Copies the file as the Administrator user using WinRM
provisioner "file" {
  source      = "conf/myapp.conf"
  destination = "C:/App/myapp.conf"

  connection {
    type     = "winrm"
    user     = "Administrator"
    password = "${var.admin_password}"
    host     = "${var.host}"
  }
}
```
linux
```
# Copies the file as the root user using SSH
provisioner "file" {
  source      = "conf/myapp.conf"
  destination = "/etc/myapp.conf"

  connection {
    type     = "ssh"
    user     = "root"
    password = "${var.root_password}"
    host     = "${var.host}"
  }
}
```