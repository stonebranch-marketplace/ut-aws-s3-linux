# ut-aws-s3-linux
Universal Automation Center support for scheduling AMAZON S3 file Transfers 

# Abstract: 
The here described Universal Tasks allow to Transfer and retrieve files from Amazon AWS S3. As a result, you can integrate any AWS S3 file 
transfers into you existing or new scheduling workflows, providing a true hybrid cloud (on-premise and cloud computer) file transfer 
solution.  

# 1. 	Disclaimer

No support and no warranty are provided by Stonebranch GmbH for this document and the related Universal Task. The use of this document and 
the related Universal Task is on your own risk.

Before using this task in a production system, please perform extensive testing.

Stonebranch GmbH assumes no liability for damage caused by the performance of the Universal Tasks

# 2.	Scope 

This document provides a documentation how to install and use the Universal Tasks for AWS S3 File Transfers. If more Task will be created 
in the future this document will be updated accordingly.  

# 3.	Introduction

Storing data in the cloud becomes an integral part of most modern IT landscapes. With Universal Automation Center you can securely 
automate your AWS, Azure or any other Cloud File Transfer and integrate them into your existing scheduling flows.
As security is one of the key concerns, when moving to the cloud, the provided solution supports multi-level of security:

    •	All Credential for AWS S3 (Access Key, Secret Access key and Region) are stored in an encrypted form in the database
    •	Connections towards the AWS VPC via a Proxy Server are supported
    •	Secure access to AWS S3 buckets using AWS bucket policies can be configured
    •	Restrict sending files only to specific buckets using AWS End Points

The here described Series of Universal Tasks focuses on the AMAZON AWS S3 file transfer. A similar solution as for AWS S3 is also 
available for Microsoft Azure. 

Some details about the universal tasks for AWS S3:

    •	The Universal Tasks are calling the python module Boto3 - the Amazon Web Services (AWS) SDK for Python. Both Boto3 API Types are used the "low-level" Client API and Resource APIs. 
    •	The python boto3 module is called by a Universal Agent running on a Linux Server or Windows Server – Note: This document focuses on the Linux Version 
    •	The Server Running the Universal Agent needs to have Python 2.7.x or 3.6.x installed
    •	All Universal Task support encrypted connections via a Proxy Server
    •	All Credential for AWS S3 (Access Key, Secret Access key and Region) are stored in an encrypted form in the database
    •	You can configure all connection Parameters for the Proxy and AWS via the Universal Task
    •	You can select different log-levels e.g. Info and debug

The following Universal Task for AWS S3 have been implemented: 

Image 1:

# 4. 	Installation
# 4.1	Software Requirements
**Universal Task name:** ut-aws-s3-linux
**Related UAC XML Files for template and task:** Github repository
**Softwarte used:**

For the set-up you need:

    1.	Python 3.6 – can be installed as part of the Universal Agent
    2.	For Python the following modules are required: 
        •	Re, to support regular expression matching operations 
        •	glob, to find Unix pathnames matching a specified pattern
        •	os, to support operating system dependent commands
        •	sys, for output re-direct processing
        •	datetime, date and time stamps for messages
        •	logging, to provide logging capabilities for debug, info etc.
        •	boto3, provide the Amazon Web Services (AWS) SDK for Python
        •	botocore, Botocore is a low-level interface to a growing number of Amazon Web Services. Botocore serves as the foundation for the AWS-CLI command line utilities. 
        •	argparse, to allow testing of the Universal TPL. script on the command line
     Note: Only the module boto3 and botocore need to be added to python 3.6.x. e.g. using pip.
        •	pip install boto3
        •	pip install botocore  
    3.	Universal Controller 6.4.5.x or higher
    4.	Universal Agent 6.4.2.2 or higher installed on a Linux Server
    5.	An Amazon AWS S3 account to try it out
   
 # 4.2	Installation Steps
 
The following describes the installation steps:

**1. Check the current Python Version**

python -V  (Note: Captial “V”)

If your Version is Python 3.6 or later all is fine. If a no python or a lower Version has been installed upgrade your python Version or 
install the Universal Agent with the Python binding option (--python yes). This option will install python 3.6. along with your 
universal agent.

e.g.

    sudo sh ./unvinst --network-provider oms --oms-servers 7878@192.168.88.12 --oms-port 7878 --oms-autostart no --ac-netname OPSAUTOCONF --opscli yes --python yes

**NOTE: the above install string does not work in case you did a user mode install**

Official Download link: https://www.python.org/downloads/

Note: To check the current Python Version type in a shell: python -V (capital V)

**2. TAdd the boto3 and botocore modules to your python installation**

In a command shell run as root or sudo:
    •	pip install boto3
    •	pip install botocore

**3. Import each AWS S3 Universal Task including the Universal Template to your Controller**
Go to “All Tasks” and load via the Import functionality the Universal Task configuration into the Controller. 

 Image 2:
 
 Image 3:
 
# 5.	Universal Task Configuration
**1.	Activate: Resolvable Credentials in Universal Automation Center:**

Image 4:

**2.	Fill Out the Universal Task for each AWS command, which you want to execute:**
In the example below the S3 Boto3 Create Bucket Task was selected

Image 5:

**Fill out or select the required Credentials for AWS and optionally a Proxy Server**

In the example below the AWS-SECRET-ACCESS-KEY credentials are shown:

Image 6:


# 6. Universal Tasks for AWS S3

The following chapter describes the provided AWS S3 Universal Tasks.

# 6.1 Create-Bucket

Image 7:

**Task Screenshot:**

Image 8:

**Field Description:**

Image 9:

# 6.2 Monitor-key-in-bucket

Image 10:

**Task Screenshot:**

Image 11:

**Field Description:**

Image 12:

# 6.3 Copy-file-to-bucket

Image 13:

**Task Screenshot:**

Image 14:

**Field Description:**

Image 15:

# 6.4 List-keys-in-bucket

Image 16:

**Task Screenshot:**

Image 17:

**Field Description:**

Image 18:

# 6.5 Download-file-from-bucket

Image 19:

**Task Screenshot:**

Image 20:

**Field Description:**

Image 21:

# 6.6 Delete-key-from-bucket

Image 22:

**Task Screenshot:**

Image 23:

**Field Description:**

Image 24:

# 6.7 Delete-empty-bucket

Image 25:

**Task Screenshot:**

Image 26:

**Field Description:**

Image 27:

# 6.8 List-buckets

Image 28:

**Task Screenshot:**

Image 29:

**Field Description:**

Image 30:

# 6.9 Check-for-key-in-buckets

Image 31:

**Task Screenshot:**

Image 32:

**Field Description:**

Image 33:

# 7. Test Cases

The following basic test cases has been performed:

Image 34:

Image 35:





    






