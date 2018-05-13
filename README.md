# AWS CloudFormation Template: Rubrik CloudOn

Complete the AWS configuration process required for the Rubrik CloudOn feature which provides the ability to convert a snapshot, an archived snapshot, or a replica into an Amazon Machine Image (AMI) and then run that AMI on an Amazon virtual private cloud (VPC).

![CloudFormation Screenshot](https://user-images.githubusercontent.com/8610203/39969410-c618e92e-56a0-11e8-9513-c34c1dae2227.png)

Variables
------------------

**Storage Configuration**

| Variable  |  Default | Description  |
|---|---|---|
| CreateS3NewBucket | no | Create a new S3 Bucket to use as a Rubrik archival location.|
| S3BucketName | n/a |The name of the S3 Bucket used as a Rubrik archival location.|

**Network Configuration**

| Variable  |  Default | Description  |
|---|---|---|
| VPC | n/a | Select the VPC for the archival location. |
| OnPremRubrikCIDR | 10.79.0.0/24 (example only) | The CIDR block for your on-prem Rubrik Cluster. |

**IAM Users and Roles**

| Variable  |  Default | Description  |
|---|---|---|
| IAMUserName | rubrik-cloudon | The name of the IAM User to assign the new CloudOn specific policies to. |
| CreateNewUser | yes | Create a new IAM user specific to Rubrik CloudOn. If 'no' is selected the S3 IAM policy will be attached to the provided IAMUserName which should already be created. |
| CreateVMImportRole |yes | Create a new VM Import Role. If the vmimport role has already been created or if another stack controls the vmimport role creation process select 'no'. |

**Optional**

Default names and descriptions for the various IAM Users, Policies, and Security Group created during the process.

| Variable  |  Default | Description  |
|---|---|---|
|SecurityGroupName | rubrik-cloudon | The name of the Security Group specific to Rubrik CloudOn. |
| SecurityGroupDescription | Security group used for Rubrik CloudOn. | The description of the Security Group configured to allow the ports required for Rubrik CloudOn. |
| SecurityGroupRoleDescription | Ports required for Rubrik CloudOn. |The description of the Security Group Ingress Role specific to Rubrik CloudOn |
| UserPolicyName |rubrik-cloudon |S3 Security policy used for Rubrik CloudOn.|
| VMImportPolicyName | rubrik-vmimport-role | Name of Rubrik CloudOn specific policy for the VM Import Role. |


Author Information
------------------

<p></p>
<p align="center">
  <img src="https://user-images.githubusercontent.com/8610203/37415009-6f9cf416-2778-11e8-8b56-052a8e41c3c8.png" alt="Rubrik Ranger Logo"/>
</p>