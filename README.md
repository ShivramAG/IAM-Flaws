# IAM-Flaws
### AWS IAM Security Toolkit: CIS Benchmarks | Enumeration | Privilege Escalation

A simple bash script that me along with my friend [Nikhil Sahoo](https://github.com/nikhil1232) have built that checks for misconfigurations in User and Group Policy Permissions in order to escalate privileges along with some additional features like CIS Benchmark checks and IAM Enumeration.

![Image of IAM-Flaws](https://github.com/nikhil1232/IAM-Flaws/blob/master/images/iam-flaws.png)


**It is recommended to go through this Blog before proceeding:**</br>
https://medium.com/@amirthashivram/iam-flaws-exploiting-user-and-group-policies-in-aws-iam-952a4c7a63d2

As of now, the script supports the following activities:

- All CIS Benchmark checks related to AWS IAM
![Image of IAM-Cis-Benchmark Checks ](https://github.com/nikhil1232/IAM-Flaws/blob/master/images/iam-cis-benchmark.png)</br></br>
- AWS IAM Enumeration of Users, Groups, Policies and Permissions
![Image of IAM-Enumerate ](https://github.com/nikhil1232/IAM-Flaws/blob/master/images/iam-enumeration.png)</br></br>
- Privilege Escalation Scanning
![Image of IAM-Cis-Privesc Scanning ](https://github.com/nikhil1232/IAM-Flaws/blob/master/images/iam-privesc-scan.png)</br></br>
- Privilege Escalation Exploitation
![Image of IAM-Cis-Privesc Exploitation ](https://github.com/nikhil1232/IAM-Flaws/blob/master/images/iam-privesc-exploit.png)</br></br>

## Requirements
<code>git clone https://github.com/ShivramAG/IAM-Flaws/ </code> </br>
<code>cd IAM-Flaws</code></br>
<code>pip install -r requirements.txt</code></br>
<code>apt-get install jq</code></br>



Once awscli is installed, you need to configure it using the **aws configure** by providing the access and the secret key of the IAM user.

Now coming to permissions, there are a few permissions that needs to be set for a user in order for our enumeration script to work properly and for an effective and complete enumeration.
Below is listed a few permissions that is recommended to be set for a user before proceeding with our script.

> “iam:GetUser”

> “iam:ListUsers”

> “iam:ListGroupsForUser”

> “iam:ListGroupPolicies”

> “iam:GetGroupPolicy”

> “iam:ListAttachedGroupPolicies”

> “iam:GetPolicy”

> “iam:GetPolicyVersion”

> “iam:ListUserPolicies”

> “iam:GetUserPolicy”

> “iam:ListAttachedUserPolicies”

These permissions could be set either through the awscli or directly through the console, however if you don’t provide these permissions, the script will try to enumerate as much as possible based on the permission a certain user has.


## Usage 
#### <code>bash iam-flaws.sh</code>

There are 3 different modules/scripts for benchmark checks, enumeration and privilege escalation respectively and all the 3 of them could be run independently, however it is highly recommended to use iam-flaws.sh directly which is kind of a central script through which you could select any of the module and it would also help in storing your output to a file.


## Thanks 
Thanks to Rhino Security Lab for this amazing list of 21 privilege escalation methods.
https://rhinosecuritylabs.com/aws/aws-privilege-escalation-methods-mitigation/
