# TERRAFORM SYNTAX

The Terraform language syntax is built around two key syntax constructs: arguments and blocks.

**HCL** 
```
resource "aws_instance" "example" {
  lifecycle {
    create_before_destroy = true
  }
}
```
**JSON**
```
{
  "resource": {
    "aws_instance": {
      "example": {
        "lifecycle": {
          "create_before_destroy": true
        }
      }
    }
  }
}
```