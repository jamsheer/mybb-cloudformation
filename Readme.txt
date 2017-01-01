Deliverables:

Created template can be deployed in CloudFormation Management Console 
and it will create complete stack to serve scalable
LAMP application with minimum information needed to set it up.

AWS Management Console Sign-in URL is
https://565116797498.signin.aws.amazon.com/console

login:crossover
password:Ec50@z#vVZOC

There is presently one stack created in eu-west-1,
crossover user has read-only privileges for all the AWS services.

Output tab of stack in CloudFormation Management Console contains ELB URL where 
deployed application can be found.

login:admin
password:nimda123

Assumptions:

MyBB is bulletin board software so for this project, it is publicly accesible. 
Backend database need to be accessible only from frontends.
There is pre-created key-pair for access to EC2 instances.
Architecture should support scale-out with multiple frontends,
with loadbalancer must be in front to distribute the load.
AZ can fail, so project will support multi AZ deployment.
Instance and database sizes are limited to restrict costs while testing.
Domain to present deployment is external to AWS, so CNAME record should point 
to ELB FQDN, with low TTL to be flexible on stack rebuilds.
Stack is ment to be deployed only over single region.

Not covered:

I did not covered Management System as i do not have enough time to elaborate on it.
From fast check on requirements, combination of MyBB admin panel and AWS Management 
Consoles will cover statistics and configuration of the deployment, so application 
should possibly be only wrapper on top of these.

Issues:

I started the CloudFormation template based on Wordpress template, and added needed 
features.
Final template is quite large and somehow hard to navigate.

What can be improved:

Deployment can be https only.
Route 53 integration.
Cloudfront as CDN with images and uploads hosted on S3 or dedicated instances to serve.
Management access relies on user supplied ACL, VPN access for management will be more 
secure, but more complex to manage.
Split template into multiple parts, or changesets.
