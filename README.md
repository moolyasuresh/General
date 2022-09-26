Pros:
1. AWS Config rules can be deployed across multiple accounts in an Organization
2. Scalable, consistent and efficient 
3. Follows DevOps practices
4. Uses RDK and RDKlib
5. Decouples compliance rule development, review and deployment
6. Through the use of GitLab and CodeCommit, it facilitates change management of compliance rules
7. It scales well with an increasing number of AWS accounts and centralize compliance management when using a distributed organization model.
8. Reduce the maintain effort by moving boilerplate code to an AWS Lambda layer (RDKLib)


Cons:
1. Only 150 organization rule can be deployed. This is the hard limit .
2. Need to deploy IAM role for the lambda function to verify rule compliance on every account using stack set
3. For each custom rule, there will be a lambda function.


Developer would create new custom rules using CFN Guard. If they have more complex rules and all the Configuration Items are not available then they would create a rule using RDK. Both AWS Managed rule and custom rules would be part of Conformance pack. Developer would check in the code to GitLab and it then triggers the pipeline. The delegated account would have the CI/CD pipeline setup.
Build scripts in CodeBuild would  deploy multiple conformance packs to AWS Organization using CLI (PutOrganizationConformancePack API with excluded AWS Accounts). Since we need to deploy set of rules to specific OUs, we need to exclude some of the AWS accounts as OU deployment is currently not supported in AWS Config.
Develop branch in GitLab would deploy to DEV AWS Organization and master to QA/Hom and Prod AWS Org. Each AWS org has ~2000 AWS accounts.
All configuration snapshots and history will be stored in central S3 bucket. All AWS accounts would send the configuration change events to central SNS topic which is subscribed by SQS .
Optional- To visualize AWS Config data use Athena and Quicksight.
