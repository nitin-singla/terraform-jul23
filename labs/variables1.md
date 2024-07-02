### Lab: Variables - 1

1. Which of the following is not a valid `variable type`?
* object
* tuple
* list
* map
* item

---

2. Which one of the below is not a valid data type in `terraform`?
* set
* map
* tuple
* array
* list

---

3. Which type does the variable called `number` belong to?

(variables.tf)
```hcl
variable "name" {
    type = string
    default = "Mark"
 }
variable "number" {
    type = bool
    default = true
 }
variable "distance" {
    type = number
    default = 5
 }
variable "jedi" {
    type = map
    default = {
    filename = "/root/first-jedi"
    content = "phanius"
    }
 }

variable "gender" {
    type = list(string)
    default = ["Male", "Female"]
}
variable "hard_drive" {
    type = map
    default = {
         slow = "HHD"
         fast = "SSD"
    }
}
variable "users" {
    type = set(string)
    default = ["tom", "jerry", "pluto", "daffy", "donald", "jerry", "chip", "dale"]

 }
```

* number
* bool
* string
* list

---

4. How would you fetch the value of the key called `slow` from the variable called `hard_drive` in a `terraform` configuration?
This variable is defined in the file `variables.tf`.

* `var.hard_drive.0`
* `var.hard_drive[0]`
* `hard_drive[“slow”]`
* `var.hard_drive.slow`
* `var.hard_drive[“slow”]`

---

5. What is the index of the element called `Female` in the variable called `gender`?
Female
* `var.gender[“female”]`
* 3
* 0
* 1

---

6. What is the type of variable called `users`?

* `set`
* `list(string)`
* `list`
* `set(string)`

---

7. However, this variable has been defined incorrectly! Identify the mistake.

* type used is incorrect
* syntax error
* duplicate elements
* elements not be enclosed in double quotes

--- 

8. We have now updated the `main.tf` file and added some resource blocks. Inspect them.

```hcl
resource "local_file" "jedi" {
    filename = "/root/first-jedi"
    content = "phanius"
}
```

---

9. What is the value for the argument called content used in the resource block for the resource `jedi`?

* obi-wan
* yoda
* first-jedi
* phanius
* jedi

---

10. Now, let's update this resource and add variables instead. Use the default value declared 	in the variable called `jedi`.


 This variable is a map. For the argument called `content` use the value of the key by the same name.
And, similarly, for the argument called `filename` use the value by the same name.

When ready, run `terraform init`, `plan` and `apply` to create this resource.


