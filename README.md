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
        // Jenkinsのクレデンシャルを使用して、Artifactoryサーバを作成します。
        // Gradleビルドを作成します。
        // リゾルバをGradleビルドに設定し、Artifactoryから解決します。
        // デプロイヤをGradleビルドに設定してArtifactoryにデプロイします。
        // GradleスクリプトがArtifactoryプラグインを使用しない定義をします。
        // GradleスクリプトがGradleラッパーを使用する定義をします。
    }
    stage('Build') {
        //GradleタスクのartifactoryPublishを実行し、ビルド情報を収集します。
    }
    stage('Publish Build Info') {
        //環境変数をビルド情報に収集します。
        //ビルド情報をパブリッシュします。
    }
}
```
