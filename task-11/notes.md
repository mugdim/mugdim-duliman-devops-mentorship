# TASK-11: AWS Tools GitFlow Workshop  
## Week 13  
Za ovaj task bilo je potrebno pratiti workshop sa 
[linka](https://catalog.us-east-1.prod.workshops.aws/workshops/484a7839-1887-43e8-a541-a8c014cd5b18/en-US/introduction). 
U nastavku ovog dokumenta su prikazani screenshot-ovi izvršenih demo/dijelova taska. 
Komentare sam stavio tamo gdje mi se razlikovalo u odnosu na workshop i gdje sam se susreo sa 
problemom.  

## Access AWS Cloud9 IDE  
 
Nakon kreiranja Cloud9 environmenta prosirio sam storage.  

![Level 0](slike/df-h.png)  

![Level 0](slike/resize.png) 

## Initial Setup  

Podesio sam github kofiguraciju i instalirao gitflow.  
 
![Level 0](slike/githubname.png)  

![Level 0](slike/gitflow.png)  

## AWS Cloudformation  
### Master Branch  
Podesavanje infrastrukture i aplikacije.  

![Level 0](slike/create_codecommit.png)  

![Level 0](slike/codecommit.png)  
![Level 0](slike/download_sampleapp.png)  
![Level 0](slike/unzipgitflow.png)  
![Level 0](slike/beanstalk.png)  

Nakon ovog koraka izmijenio sam unutar file envcreate.yaml verziju Amazon Linux-a u 
SolutionStackName: "64bit Amazon Linux 2 v5.8.1 running Node.js 16".
Potrebno je bilo dodati i novi IAM rolu pod nazivom *aws-elasticbeanstalk-ec2-role* da EC2 
instance imaju permisije nad elasticbeanstalk.

![Level 0](slike/IAMrole.png)  
![Level 0](slike/stack_master_env.png)  
![Level 0](slike/beanstalk_env.png)  
![Level 0](slike/pipeline.png)  
![Level 0](slike/app_1.png)  

### AWS Lambda  
Prije kreiranja Lambdi unutar S3 bucketa kreiranog kroz stack podesio sam defaultnu 
enkripciju kao na slici ispod.  
![Level 0](slike/S3_bucket_KMS.png)  
Kopirao sam ARN ključa i napravio dokument .elasticbeanstalk, kojeg sam stavio u zip i 
upload-ovao na S3 bucket. File lambda/lambda-create.yaml sam izmijenio da sam naziv S3 
bucketa stavio naziv svog S3 bucketa i S3Key naziv uploadovanog kljuca.U istom file sam 
izmijenio naziv policya za usera. Ovaj file je dostupan 
unutar foldera all-files-and-dirs-used-for-this-task.  

![Level 0](slike/stack_lambda.png)

#### AWS CodeCommit Trigger
  
![Level 0](slike/trigeri.png)  

### Develop Branch
![Level 0](slike/git_develop.png)  
![Level 0](slike/dev_env.png)  

### Feature Branch  
 
![Level 0](slike/change_color.png)  
![Level 0](slike/app_feature_branch.png)  
![Level 0](slike/komande_feature_branch.png)  


