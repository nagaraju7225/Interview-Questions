### about jenkins enverloment?
+ currently we are working on a java based applocation, And use maven as build tool,sonar qube as code analysis, jfrog as artifact. 
+ we have dev, stage, perf, prod envronments the strategy and we mantain separate build for these envronments and segregate them in folder wise. Access is given to dev teams on dev,& stage,Devops and application support teams have full access on all env. 
+ In prod we have 3 builds which deploy to 3 different data center zones, and on the folder level we maintain the credentials of bitbucket, vault, api tokens for splunk and dynatrace, which differ for all env.

### What is the branching strategy you are using? 
+ As part of the dev activity they are current using master, Devops feature, branches.
+ Developers work on feature branches and push there changes to develop 
+ Branches we have DEV, STAGE, UTA, PROD env, DEV env. Build uses develop branch STAGE, 
+ UAT, PROD uses master branch.We have a hotfix branch which is created when an issue occurs in higher env and once changes are done its merged back to master. We maintain the version tags for the releases.
  
### What kind of Jenkins setup you have?
+ currently we have declarative pipeline jobs freestyle, multi branch jobs.
+ We have differentiated the builds on ENV basis, for Dev, STAGE, UTA, PROD.
+ So dev team has edit access on dev build, rest all admin access is with my team.

### What kind of Jenkins jobs you have in your environment
+ We have differentiated the builds as per the env, In dev we have a multibranch  pipeline,dev deploy pipeline, artifact upload pipeline, and in stage we have stage deploy and in UAT we have same deploy pipeline and in Prod we have 3 deploy pipelines for each datacenter.
+ Apart from we have some testing pipelines for jmeter, performance testing, and cucumber based and cert refresh pipelines.

### How to Install Git Plugin in Jenkins?
+ 1) Click on the Manage Jenkins button on your Jenkins dashboard
  2) Click on Manage Plugins 
  3) In the Plugins Page Select the GIT Plugin Click on Install without restart.
+ Once the plugins have been installed, go to Manage Jenkins on your Jenkins dashboard.You will see your plugins listed among the rest.
  1) Create a new job in Jenkins 
  2) Enter the item name, select job type and click OK. We shall create a Freestyle project 
  3) Once you click OK 
  4) Source Code Management Git option as mentioned above click.
  5) Enter the Git repository URL to pull the code from GitHub.save and apply

### What is shared library in Jenkins example?
+ A shared library in Jenkins is a collection of Groovy scripts shared between different Jenkins jobs.To run the scripts, they are pulled into a Jenkinsfile.
+ Each shared library requires users to define a name and a method of retrieving source code.
### What is devops?
+ DevOps is the combination of cultural philosophies, practices, and tools that increases an organization's ability to deliver applications at high velocity,and improving products at a faster pace than organizations using traditional software development and infrastructure management processes.
### Have you written any pipeline scripts or created any new pipelines?
+ Yes, I have created and written few pipeline scripts mostly related to build and deploy.
+ Which has compilation, testing, sonar , artifact upload and deployment and notification stages.One of the recent pipeline.
+ I have written is for testing for JMH benchmarks for java application.
+ I have used parameters options for giving duration and threads, 
and in the stages it will pick these values and hit the app url and waits until the tests are completed, Once tests are completed 
it will pick the report and mail them to dev team,if it fails due to any issue it triggers a mail to my team. 
+ Apart from these pipelines we have multi branch pipelines and release version based deployment and cert renewal of the app pipelines. 
+ I have knowledge in groovy scripting based on the requirement
I search for the respective libraries and write the stages in the pipeline. 

### what is different between Declaritive pipeline and scripting pipleline?
+ It is a technique used to maintain the continuous integration and continuous deployment workflow in code respiratory,
without any requirement of any configurations of branch.It includes the declarative pipeline and script pipeline syntax
1. Declarative pipeline : It is used for simple way for designing the pipelines, the complete pipeline as pects are controlled

syntax: 
``` Jenkins Declarative pipeline
pipeline{
       agent any;
       stages { (build )
        stage {   (testing)
          steps{  (deploy) }
        }
       }
}
```
2. Script pipeline: By using the execution of the lightweight jenkin runs, it is helpful for code as a pipeline.

synatx: 
``` jenkins script pipeline
node {
       stages{ (build )
        stage{   (testing)
         steps{  (deploy)
         }
        }
     }
}
```
### What is the build tool you are using and what kind of application?
+ I am working for a java based application and we use maven as a build tool.

### For which client you are working?
+ Currently I am working a investing banking client based in US.

### what is devops different from agile methodology?
+ The diffence between agile methodology and devops is that, agile methodology is implemented only for development section and devops implements agile on both development as well as opetations section.

### What is CI, CD, CD?
+ **Continuous Integration** , which is an automation process for developers where new code changes to an app are regularly built, tested, and merged to a shared repository.
+ **Continuous Deployment** can refer to automatically releasing a developer's changes from the repository to production with all the necessary testing done automatically.
+ **Continuous Delivery** is the process releasing more number of versions of the code and making it available to customers.

### Describe agent directory?
+ It is used to direct the jenkin for the pipeline's execution, they need an agent which creates allocation and includes checkout files,that is essential for pipeline.
### Standard freestyle options?
+ General, source code managment , Build triggers, Build environment, build, post-build actions

### pipeline script options? 
+ General, build triggers, advanced project options, pipeline

### Jdk and maven are integrated in jenkins?
+ Yes, i have integrated JDK and maven for this
jenkins dashbord -> Go to manage jenkins click on -> Global tool configuration -> Click on JDK installation and set JAVA_HOME path -> Click on Maven Installation and set Maven path.
( or ) check Install automatically checkbox Finally click on save and your Maven configuration is done.

### Agents connection methods jenkins?
+ 3 types of Agents connection methods in jenkins 
   1) JNLP method
   2) SSH method
   3) Key based authentication.

### What is Jenkins?
+ Jenkins is a self-contained, open-source automation server that can be used to automate all sorts of tasks related to building,testing, and delivering or deploying software.
+ Jenkins can be installed through native system packages, Docker,or even run standalone by any machine with a Java Runtime Environment (JRE) installed.

### Describe a trigger. How to identify the new commit ?
+ It is described while the pipeline is executed, commit is generated every time while during integration of the jenkin.   
    --> Download and set the plugin of Git
    --> Later we can design triggers which specialize the beginning of the new build.

### what is jenkins job ?
+ project is the fundamental unit of a logical work using the jenkins automation server and other required plugins. job can be of different types like freestyle project ,multi-configuration project a pipleline project, multi-branch project ect.

### List out some variables of jenkin environment ?
+ P4_CHANGELIST
+ P4_CLIENT
+ P4_PORT
+ P4_ROOT
+ P4_USER
+ JENKINS_URL
+ WORKSPACE
+ NODE_LABELS

### List out various kinds of pipelines in jenkins ?
+ Jenkin contains 3 kinds of pipelines as given 
   1) Pipeline of continuous delivery and continuous integration
   2) Pipeline of scripted
   3) Pipeline of declarative

### Diference between the upstreem and downstreem ?
+ An upstream project is one in which a job is triggered before the actual project is triggered Where as,Downstream project is one in which a job is triggered after the project has been triggered.