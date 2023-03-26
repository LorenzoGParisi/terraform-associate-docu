# TERRAFORM LOCAL-ONLY RESOURCES

They are specialized resource types that operate only within the local machine that is running Terraform. 

They save their results in the state for future use.

**Popular local-only resources:**

- **null_resource:** 
```
resource "null_resource" "example" {

  triggers = {
    cluster_instance_ids = join(",", aws_instance.cluster.*.id)
  }

  provisioner "local-exec" {
    command = "echo 'Hello, world!'"
  }
}
```
If cluster_instance_ids changes during the apply should output the message "Hello, world!" in the console.

&nbsp;

- **local_file:** 
```
resource "local_file" "example" {
  content  = "This is an example file.\n"
  filename = "${path.module}/example.txt"
}
```
A file named example.txt will be created in the same directory as the Terraform configuration file with the contents "This is an example file.".

&nbsp;

- **local_file as a data source:** 
```
data "local_file" "foo" {
  filename = "${path.module}/foo.bar"
}

resource "aws_s3_object" "shared_zip" {
  bucket  = "my-bucket"
  key     = "my-key"
  content = data.local_file.foo.content
}
```