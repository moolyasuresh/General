How to manage AWS Services which are not supported by AWS Config? 

There are 5 AWS services- Glue, Athena, Amazon MQ, ElasticCache and Apache Airflow) are not supported in Config but used by Itau in Turbot. 

Athena and ElasticCache are on roadmap- expected in 4-12 months 

Glue , MQ and AirFlow are not yet reviewed -  

 GLue and Athena are supported 

How to measure the performance? 

When a new AWS resource is created , how much time Config would take to evaluate and show the compliance result? - Real time? Near real time? 

How to verify the response time for re-evaluation of rules? 

Decide on the tool – CFN Guard vs RDK vs CFT vs Terrraform 

Currently CFN Guard is not supported by CFT 

AWS Config best practices suggests to use RDK as it provides an option to deploy the rules to AWS Organizations and as well multi-accounts 

CFT- difficult to fit all the rules in one template?.  

RDK  and Guard supports Terraform- Isaish to send links 

Decide on the deployment method- Multiple accounts vs Organization Vs Control tower? 

How to process events- Aggregator  vs Audit Manager 

AWS Config new features- CloudTrail lake , Built in score engine for Conformance pack is available now. For Managed and custom rules? 
