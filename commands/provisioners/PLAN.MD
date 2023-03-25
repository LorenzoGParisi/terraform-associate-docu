# TERRAFORM PLAN

**What does it do?**

- Refresh or creates state file.

- Generates a plan for future infrastructure changes that will be executed if an apply command is run.

```
terraform plan -var-file=variables.tfvars -out=tfplan -workspace=prod

```

**Warning:** 

- -out=FILE/path-to-file option to save the generated .tfplan (also backend configuration are saved in it).

- -destroy it generates a destroy plan.

- -refresh-only it refreshes only the state and it not returns a plan.