## Lab: Using Variables in terraform

1. How can we use `environment` variables to pass `input variables` in `terraform` scripts?

* `TF_VAR_<variable_name>`
* `.tf`
* `export variable`
* `.var`

- - -

2. Which method has the highest priority in Variable Definition Precedence?
If unsure, Refer to the documentation.
* using `.auto.tfvars`
* variable definition file `terraform.tfvars.json`
* using `terraform.tfvars`
* command line flag `-var` or `-var-file`

- - -

3. Which command is a valid way to make use of a custom variable file with the `terraform apply` command?

- - -

4. We have created some files under the directory `/dir1`. Inspect it.

`basket.auto.tfvars`
```hcl
filename = "./basketball.txt"
```

`main.tf`
```hcl
resource local_file games {
 filename = var.filename
 content = "football"
}
```

`terraform.tfvars`
```hcl
filename = "./football.txt"
```

`throw.auto.tfvars`
```hcl
filename = "./baseball.txt"
```
- - -

5. What will happen if we run the `terraform plan` command right now?
* Error
* Success

- - -

6. The `terraform plan` command did not run as there was no reference for the input variable called `filename` in the configuration files.
Let's fix that now.

- - -

7. Declare the variable called `filename` with type `string` in the file `variables.tf`.
Don't have to specify a `default` value.

- - -

8. If we run `terraform apply` with a `-var` command line flag as shown below, which value would be considered by `terraform`?
```hcl
terraform apply -var filename=./tennis.txt
```

