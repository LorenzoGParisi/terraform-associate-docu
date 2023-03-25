# TERRAFORM GET

**What does it do?**

Downloads and updates modules mentioned in the root module.

Using -update modules that are already downloaded will be checked for updates and the updates will be downloaded if present.

It creates:

- Everytime a .terraform directory with a modules.json file even with empty values in it.

```
└── .terraform
    └── modules
        └── modules.json
```

**Warning:** 

- You can use terraform init instead, for example you can use init -upgrade in the place of get -update.

- You can run terraform get in directories that do not contain any .tf files, unlike terraform init.