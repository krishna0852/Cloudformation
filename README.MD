AWS workshop on cloudformation 

This repository contain all topics and lab tasks which are learned from below worshop link

https://catalog.workshops.aws/cfn101/en-US


Package&Deploy:

package&Deploy is used to refer files to your template and then package, validate, deploy

main file should with template extension

packaging: 
===========

 aws cloudformation package \
	--template-file main.template \
	--s3-bucket demo-stack-bucket-i \
	--s3-prefix cfn-workshop-package-deploy \
	--output-template-file main-packaged.template

files will get uploaded and if you want to see those files you need to unzip after downloading from your bucket

eg: unzip -l ce6c47b6c84d94bd207cea18e7d93458


validate: 
=============

aws cloudformation validate-template \
--template-body file://main-packaged.template


Deploy:
=========
aws cloudformation deploy \
--template-file main-packaged.template \
--stack-name cfn-workshop-package-deploy-lambda \
--region us-east-1 \
--capabilities CAPABILITY_IAM

============


Cloudformation Topics: 
============================

Parameters 
metadata
InternsicFunctions  (!Ref, !Sub !GetAtt)
Psuedo paramers 
output 
mappings 
return values 
conditions
Dynamic Reference 
depennds on 
Language extensions 
nested stacks 
cross stacks 
package&deploy 
foreach 
architect templates 
changeset 
stack-policies-prevention 
resource import


