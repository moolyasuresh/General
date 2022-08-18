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
