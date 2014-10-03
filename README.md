IMPORTANT!
==========

Before running this play, create an awscreds.conf file in roles/common/files or set up your instances with a role. The credentials or tole you use should have the CloudWatch:putmetric permission.
The format for awscreds.conf is:


>AWSAccessKeyId= //enter key ID here  
>AWSSecretKey= //enter secret key here


You can also pass variables for "hosts", "user", "interval", and "script_dir" with -e  
These variables control the hosts that are being deployed to, the user that is used for the deployment, the cron interval in minutes, and the directory that the CloudWatch scripts will be stored in.

The defaults for these are "ec2", "smiller", "5", and "/var/local/cloudwatch/"
