IMPORTANT!
==========

Before running this play, create an awscreds.conf file in roles/common/files or set up your instances with a role. The credentials or tole you use should have the CloudWatch:putmetric permission.
The format for awscreds.conf is:


>AWSAccessKeyId= //enter key ID here  
>AWSSecretKey= //enter secret key here


Run deploy.yaml to only push the metrics, and run create-alarm.yaml to push the metrics and create alarms based on them. create-alarm.yaml is currently configured to create alarms that alert when a disk is beyond 75% full.

The following variables are included and can be overwritten by passing them with -e

>hosts: ec2  
>user: smiller  
>serial: 10  
>max_fail: 20%  
>script_dir: /var/local/cloudwatch/  
>iam_role: false  
>topic: arn:aws:sns:us-east-1:406822941806:infrastructure_alarms  

Available arguments are listed below. These can be added or removed in roles/common/tasks/cron.yaml

>--mem-util          Reports memory utilization in percentages.  
>--mem-used          Reports memory used in megabytes.  
>--mem-avail         Reports available memory in megabytes.  
>--swap-util         Reports swap utilization in percentages.  
>--swap-used         Reports allocated swap space in megabytes.  
>--disk-path=PATH    Selects the disk by the path on which to report.  
>--disk-space-util   Reports disk space utilization in percentages.  
>--disk-space-used   Reports allocated disk space in gigabytes.  
>--disk-space-avail  Reports available disk space in gigabytes.  
>   
>--apache-worker     Reports Apache Worker Prosess counts.  
>--nginx-worker      Reports nginx Worker Prosess counts.  
>   
>--unicorn-worker    Reports Unicorn Worker Prosess counts.  
>--unicorn-memory    Reports Unicorn Worker Prosess memory.  
>   
>--mysqld-prosess    Reports MySQL Daemon Prosess counts.  
>   
>--aggregated[=only]    Adds aggregated metrics for instance type, AMI id, and overall.  
>--auto-scaling[=only]  Adds aggregated metrics for Auto Scaling group.  
>                       If =only is specified, reports only aggregated metrics.  
>   
>--mem-used-incl-cache-buff  Count memory that is cached and in buffers as used.  
>--memory-units=UNITS        Specifies units for memory metrics.  
>--disk-space-units=UNITS    Specifies units for disk space metrics.  
>   
>  Supported UNITS are bytes, kilobytes, megabytes, and gigabytes.  
>   
>--aws-credential-file=PATH  Specifies the location of the file with AWS credentials.  
>--aws-access-key-id=VALUE   Specifies the AWS access key ID to use to identify the caller.  
>--aws-secret-key=VALUE      Specifies the AWS secret key to use to sign the request.  
>--aws-iam-role=VALUE        Specifies the IAM role name to provide AWS credentials.  
>   
>--from-cron  Specifies that this script is running from cron.  
>--verify     Checks configuration and prepares a remote call.  
>--verbose    Displays details of what the script is doing.  
>--version    Displays the version number.  
