# AWS CloudFormation Template: CloudOn

Complete the AWS configuration process required for the Rubrik CloudOn feature which provides the ability to convert a snapshot, an archived snapshot, or a replica into an Amazon Machine Image (AMI) and then run that AMI on an Amazon virtual private cloud (VPC).

Amazon S3 Template URL
------------------
[https://s3-us-west-1.amazonaws.com/cloudformation-templates-rubrik-prod/rubrik_cloudon.template
](https://s3-us-west-1.amazonaws.com/cloudformation-templates-rubrik-prod/rubrik_cloudon.template
)

![Select Template](https://user-images.githubusercontent.com/8610203/39970416-9d6bd71a-56b0-11e8-8a58-7832875180a8.png)

CloudFormation Stack Interface
------------------

![CloudFormation Screenshot](https://user-images.githubusercontent.com/8610203/40571753-2e30a05c-6064-11e8-9569-489446ce5bc7.png)

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

Output
------------------

| Variable | Description |
|---|---|
| IAMUserAccessKey | Access Key for the new IAM User.  (if applicable) |
| IAMUserSecretKey | Secret Key for the new IAM user.  (if applicable) |
| SecurityGroupId | ID for the newly created Security Group |
| VPCId | VPC ID where the Rubrik Bolt Instance is created. |



Author Information
------------------

<p></p>
<p align="center">
  <img src="https://user-images.githubusercontent.com/8610203/37415009-6f9cf416-2778-11e8-8b56-052a8e41c3c8.png" alt="Rubrik Ranger Logo"/>
</p>
