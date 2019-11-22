# Gradleを利用したArtifactory Challenge
Artifactory ChallengeのGradleサンプル

プロジェクトをビルドする方法は[Artifactory Jenkins plugin documentation](https://www.jfrog.com/confluence/display/RTF/Working+With+Pipeline+Jobs+in+Jenkins)をご参照ください。

1. Artifactoryインスタンスを取得します。[(オンプレミスまたはクラウド版のフリートライアルを利用可能です)](https://jfrog.com/ja/artifactory/free-trial/)
1. Jenkinsをインストールします。
1. Artifactory Jenkinsプラグインをインストールします。
1. JenkinsクレデンシャルにArtifactoryクレデンシャルを追加します。
1. 新規のパイプラインジョブを作成します。
1. 以下のスクリプトを完成するために[Artifactory Plugin DSL documentation](https://www.jfrog.com/confluence/display/RTF/Working+With+Pipeline+Jobs+in+Jenkins#WorkingWithPipelineJobsinJenkins-GradleBuildswithArtifactory)をご参照ください:

```
node {
    def rtServer
    def rtGradle
    def buildInfo
    stage('Preparation') {
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
