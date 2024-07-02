### Lab: Terraform Providers

1. We have a new configuration. Inspect its directory and find out the number of providers initialized within this directory.
Do not run `terraform init` yet!

```hcl
resource "local_file" "things-to-do" {
 filename     = "/root/things-to-do.txt"
 content  = "Clean my room before Christmas\nComplete the CKA Certification!"
}

resource "local_file" "more-things-to-do" {
 filename     = "/root/more-things-to-do.txt"
 content  = "Learn how to play Astronomia on the guitar!"
}
```


* 0
* 1
* 2
* 3
* 4
* 5


2. After running `terraform init`. How about now? How many provider plugins are installed in this configuration directory?

```hcl
resource "local_file" "things-to-do" {
 filename     = "/root/things-to-do.txt"
 content  = "Clean my room before Christmas\nComplete the CKA Certification!"
}

resource "local_file" "more-things-to-do" {
 filename     = "/root/more-things-to-do.txt"
 content  = "Learn how to play Astronomia on the guitar!"
}
```

* 0
* 1
* 2
* 3
* 4
* 5

3. (Later)

4. How many resources are configured in this configuration directory?
Count all the resource blocks used.
* 0
* 1
* 2
* 3


5. What is the version of the plugin for the local provider that has been downloaded for this configuration? (Try this yourself)


6. Now, go ahead and create these resources using terraform!
Once done, the two files defined inside the resource blocks should be created with the correct file names and content.

7. We have created another directory containing configuration files.
Inspect this configuration directory.

cyberpunk.tf
```hcl
resource "local_file" "cyberpunk" {
 filename     = "/root/cyberpunk2077.txt"
 content  = "All I need for Christmas is Cyberpunk 2077!"
}
```

ps5.tf
```
resource "local_file" "ps5" {
 filename     = "/root/ps5.txt"
 content  = "And a PS5!"
}
```

8. How many resources are configured within this configuration directory?
Make sure to check all the `.tf` files.
* 2
* 0
* 5
* 1


9. What is the `filename` that will be created by the resource called `cyberpunk`?

* `/root/cyberpunk.txt`
* `cyberpunk`
* `/root/ps5.txt`
* `/root/cyberpunk2077.txt`


10. Create a new configuration file within the same directory called `xbox.tf`. This file should make use of the same `local_file` resource type with the below requirements:

> Resource Name: `xbox`

> filename: `/root/xbox.txt`

> content: `Wouldn't mind an XBox either!`


Once the configuration file has been created, use the terraform workflow to create this resource.


