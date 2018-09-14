# gradle-example
Simplest Gradle example for JFrog Jenkins Challenge.

Use [Artifactory Jenkins plugin documentation](https://www.jfrog.com/confluence/display/RTF/Working+With+Pipeline+Jobs+in+Jenkins) to build the project.

1. Get an Artifactory instance [(you can start a free trial on prem or in the cloud)](https://jfrog.com/artifactory/free-trial/)
1. Clone this repository
1. Install Jenkins
1. Install Artifactory Jenkins Plugin
1. ~~Set up JDK in Global Tool Configuration~~
1. ~~Set up Artifactory in System Configuration~~ 
1. Add Artifactory credentials to Jenkins Credentials
1. Create a new pipeline job
1. Use the [Artifactory Plugin DSL documentation](https://www.jfrog.com/confluence/display/RTF/Working+With+Pipeline+Jobs+in+Jenkins#WorkingWithPipelineJobsinJenkins-GradleBuildswithArtifactory) to complete the following script:
```node {
   stage('Preparation') {
      // Get the code from a GitHub repository
      git 'https://github.com/jbaruch/gradle-example.git'
      // create a new Artifactory server using the credentials defined in Jenkins 
      // create a new Gradle build
      // set the resolver to the Gradle build to resolve from Artifactory 
      // set the deployer to the Gradle build to deploy to Artifactory
      // declare that your gradle script does not use Artifactory plugin
      // declare that your gradle script uses Gradle wrapper
   }
   stage('Build') {
      //run the artifactoryPublish gradle task and collect the build info
   }
   stage('Publish Build Info') {
      //collect the environment variables to build info
      //publish the build info
   }
}
```
