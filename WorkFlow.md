# 1. work flow
```
  Code PR -- GitHub -- Jennkins Pipeline ---Cloud

  IF something pushed in MASTER/DEV Branch :
        BUILD
        TEST
        DEPLOY by 'Npm START' in Jenkins NODE-JS AGENT

        --> You can see a website at xxxxxxjenkins-agent-url:3000

  If something pushed in Prod Branch: 
       BUILD
       TEST
       DEPLOY by 'NPM RUN BUILD' ---> upload THE build Folder to a Hosting e.g. S3 / Azure Blob
                                            
  
      ----> Folder upload to s3, you can use s3 url to visit the website ---> CLOUDFRONT(CDN) --->ROUTE 53 DOMAIN
   ```
# 2.WHAT I NEED
  ## 1 JENKINS ON EC2 OR VM
```
      create a ec2 for Master Jenkins
      open port 8080 /3000 if build-in node /50000
      ssh to ec2
      install java
      install jenkins
      ----
      Create a ec2 for Slave Jenkins
      on Agent Node -->
      install Node JS ... version issue ?
      ** slave机子上 也要装java ！！！
```
      
  ## 2 play JENKINS CONTROLLER. with One Agent 
```
     go in to jenkins
      -initialize ?
      
     plugin install 
         -- CREDITONALS
         -- FOR AWS
         -- FOR AZURE
         --BLUE OCEAN
         ??
     
     JENKINS SCRIPT-
     -Jenkinsfile
     -connect to github ? webhook? git token?
     
     
     
 ```

  ## 3 code dockerize
```
      NO.  FRONT end does not need to dockerize.
      
 ```
## 4 deploy
```
    For dev
    -CREATE agent Jenkins
    
    
     IF something pushed in MASTER/DEV Branch :
        BUILD
        TEST
        DEPLOY by 'Npm START' in Jenkins NODE-JS AGENT

        --> You can see a website at xxxxxxurl:3000
    
    
    For Prod
    -Create a S3
    -Open port
    -security group?
    
      If something pushed in Prod Branch: 
       BUILD
       TEST
       DEPLOY by 'NPM RUN BUILD' ---> upload THE build Folder to a Hosting e.g. S3 / Azure Blob
                                            
  
      ----> Folder upload to s3, you can use s3 url to visit the website ---> CLOUDFRONT(CDN) --->ROUTE 53 DOMAIN
```
