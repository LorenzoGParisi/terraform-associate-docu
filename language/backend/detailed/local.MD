# LOCAL BACKEND

The default backend saved as a plain text in the current working directory.

It supports path and worspace_dir.

```
terraform {
  backend "local" {
    path = "relative/path/to/terraform.tfstate"
  }
}
```
or as a datasource from another terraform configuration that stores the backend in your local system
```
data "terraform_remote_state" "foo" {
  backend = "local"

  config = {
    path = "${path.module}/../../terraform.tfstate"
  }
}
```