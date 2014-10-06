IMPORTANT!
==========

Before running this play, create an awscreds.conf file in roles/common/files or set up your instances with a role. The credentials or tole you use should have the CloudWatch:putmetric permission.
The format for awscreds.conf is:


>AWSAccessKeyId= //enter key ID here  
>AWSSecretKey= //enter secret key here


You can also pass variables for "hosts", "user", "script_dir", and iam_role with -e  
These variables control the hosts that are being deployed to, the user that is used for the deployment, the directory that the CloudWatch scripts will be stored in, and whether or not an IAM role will be used

The defaults for these are "ec2", "smiller", "/var/local/cloudwatch/", and "false"
