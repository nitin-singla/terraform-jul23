## Lab: Resource Dependencies

1. Which argument should be used to explicitly set dependencies for a resource?
* `resource_depend`
* `dependent`
* `depends_on`
* `depend_on`

- - -

2. `Resource A` relies on another `Resource B` but doesn't access any of its attributes in its own arguments. What is this type of dependency called?
* explicit dependency
* `external_dependency`
* implicit dependency
* `internal_dependency`

- - -

3. How do we make use of `implicit dependency`?
* reference expressions
* `depends_on`
* variables
* datasources

- - -

4. In the configuration directory (`/key-generator`), create a file called `key.tf` with the following specifications:


 Resource Type: `tls_private_key`

 Resource Name: `pvtkey`

 algorithm: `RSA`

 rsa_bits: `4096`

When ready, run `terraform init, plan and apply`.

 If unsure, refer to the [documentation](https://registry.terraform.io/providers/hashicorp/tls/latest/docs/resources/private_key).

- - -

5. Resource `tls_private_key` generates a secure private key and encodes it as PEM. It is a logical resource that lives only in the `terraform state`.

 You can see the details of the resource, including the private key by running the `terraform show` command.
You can read the documentation for more details. 

- - -

6. Now, let's use the `private key` created by this resource in another resource of type `local file`. Update the `key.tf` file with the requirements:


Resource Name: `key_details`

File Name: `./key.txt`

Content: use a reference expression to use the attribute called `private_key_pem` of the `pvtkey` resource.

When ready, `run terraform init, plan and apply`.

- - -

7. Now destroy these two resources.

Use `terraform destroy`.
- - -

8. For this question, make a new directory. Within this directory, create two `local_file` type resources in the `main.tf` file.


 >Resource 1:

 Resource Name: `whale`

 File Name: `./whale`

 content: `whale`


 >Resource 2:

 Resource Name: `krill`

 File Name: `./krill`

 content: `krill`


 Resource called `whale` should depend on `krill` but do not use reference expressions.

When ready, run `terraform init, plan and apply`.

