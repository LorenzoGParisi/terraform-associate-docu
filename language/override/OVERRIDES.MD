# OVERRIDE FILES

These files are used in the same directory of the .tf files that are overrided.

Their name: override.tf or _override.tf (or json)

- The purpose of these files is to modify a .tf configuration file, without manually changing it.

**main.tf**
```
resource "aws_instance" "web" {
  instance_type = "t2.micro"
  ami           = "ami-408c7f28"
}
```
**override.tf**
```
resource "aws_instance" "web" {
  ami = "foo"
}
```
**result**
```
resource "aws_instance" "web" {
  instance_type = "t2.micro"
  ami           = "foo"
}
```

**Merging behaviour**

- Module variables: 

  the values in the override file will merge with the defaults in the module, with any defined values overriding the corresponding default values.

- Module resources: 

  the resources in the override file will be merged with the defaults in the module, with any defined resources being added to the module's resources and overriding any resources with the same name.

- Provider configuration: 

  the configurations in the override file will override the defaults in the provider, with any defined configurations overriding the corresponding default configurations.

- Data sources: 

  the data sources in the override file will merge with the defaults in the module, with any defined data sources being added to the module's data sources and overriding any data sources with the same name.

- Terraform settings: 

  the settings in the override file will merge with the defaults in Terraform, with any defined settings overriding the corresponding default settings.

- Provisoners:

  If an overriding resource block contains one or more provisioner blocks then any provisioner blocks in the original block are ignored.

- Connection:

  If an overriding resource block contains a connection block then it completely overrides any connection block present in the original block.

- Depends_on:

  The depends_on meta-argument may not be used in override blocks, and will produce an error.

- Ignore_changes:

   if an override block sets only the create_before_destroy argument then any ignore_changes argument in the original block will be preserved.

- Default:
  
  If the original block defines a default value and an override block changes the variable's type, Terraform attempts to convert the default value to the overridden type, producing an error if this conversion is not possible.

- Type:

  if the original block defines a type and an override block changes the default, the overridden default value must be compatible with the original type specification.

**Warning:** 
- Terraform initially skips these override files when loading configuration, and then afterwards processes each one in turn (in lexicographical order).