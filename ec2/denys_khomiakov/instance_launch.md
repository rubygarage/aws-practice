# Launching an EC2 Instance

Before launching an instance it is better to be aware that you are elegible for AWS `Free Tier`. You can check it in `My Billing Dashboard` section.

So, the order of actions to launch an instance is:

> Go to AWS console -> `Services` -> `EC2` -> `Instances` (*left menu*) -> `Launch Instance` ->
> Choose AMI you need (*Amazon Linux AMI 2018.03.0 (HVM), SSD Volume Type, ami-0e2ff28bfb72a4e45* would be fine for the first time, because it has Ruby and PostgreSQL pre-installed) ->
> `Select` -> `t2.micro` -> `Review and Launch` -> `Launch` -> choose `Create a new key pair` -> Enter key-pair name (*for example `key_name`*) -> `Download Key Pair` -> `Launch Instances` -> `View Instances`

Your instance was launching, and now is running.


To connect to your instance via `ssh` you have to do:

1. Check `IPv4 Public IP` on an `Instances` page (*scroll right on the running instance*).

2. Enter `chmod 400` command with the path to your key-pair `.pem` file you saved before, for example: `chmod 400 ~your_user/Desktop/key-name.pem`

3. Enter command `ssh -i path_to_your_pem_key_pair ec2-user@ip_you_checked_in_first_step`, for example: `ssh -i ~your_user/Desktop/key-name.pem ec2-user@52.87.155.123` (*`ec2-user` is default name*)

That's all! Now you are connected to your instance and can perform any actions you need. You can install any software, setup configuration you need and later save your own AMI with config you made.

When you are done, don't forget to terminate your instance to prevent charging for EC2 usage:

> `Instances` -> *Choose your instance* -> `Actions` -> `Instance State` -> `Terminate`
