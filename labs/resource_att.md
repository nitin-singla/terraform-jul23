## Lab: Resource Attributes

1. We have a configuration directory (`dir1/`). Inspect the files inside it.

`main.tf`
```hcl
resource "time_static" "time_update" {
}
```

- - -

2. What is the `resource_type` of the resource that's currently defined in the `main.tf` file?
If unsure, refer to the [documentation](https://registry.terraform.io/providers/hashicorp/time/latest/docs/resources/offset).
* `time_stamp`
* `time`
* `time_static`
* `time_update`

- - -

3. As you can see, the resource block is empty. This is because `time_static` does not need any arguments to be supplied to work.

When applied as it is, `terraform` creates a logical resource locally (similar to `random_pet`) with the current time.


- - -

4. Which of the following `attributes` are exported by the `time_static` resource?
If unsure, refer to the documentation.
* `id`
* `content`
* `filename`
* `century`
* `decade`
- - -

5. How do we refer to the attribute called `id` using a reference expression?

* `time_static[“id”]`
* `time_static_time`
* `time_update.id`
* `time_static.time_update.id`
* `time_static.time_update[“id”]`

- - -

6. Now, update the `main.tf` file and add a new `local_file` resource called `time` with the following requirements:
filename: `{path.module}/time.txt`
content: `Time stamp of this file is <id from time_update resource>`


 Use a reference expression and interpolation.

When ready, run `terraform init, plan and apply`.

- - -

7. What is the attribute called `id` that is created for the `local_file` resource called `time`?
Make use of the `terraform show` command and identify the attribute values.

- - -

8. What is the attribute called `rfc3339` that is created for the `time_static` resource called `time_update`?
Make use of the `terraform show` command and identify the attribute values.

