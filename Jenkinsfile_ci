pipeline {
    agent any

    tools {
            maven 'maven_3.9.3'
        }

    stages{
    stage('Git checkout'){
        steps{
            git branch: 'feature_gunjanm', changelog: false, credentialsId: 'ibt', poll: false, url: 'https://github.com/IBT-learning/ibt-maven.git'
        }
    }
    stage('Validate'){
        steps{
            withMaven(maven: 'maven_3.9.3') {
                sh 'mvn validate'
            }
        }
    }
    stage('Compile'){
        steps{
            sh 'mvn -version'
            sh 'mvn compile'
        }
    }
     stage('Test'){
            steps{
                sh 'mvn test'
            }
        }
      stage('Package'){
             steps{
                 sh 'mvn package'
             }
         }
       stage('Upload to Artifactory'){
        steps{
            withCredentials([file(credentialsId: 'mvn_settings_gunj', variable: 'mvn_settings_gunjan')]) {
                sh 'mvn deploy -s $mvn_settings_gunjan'
            }
        }
       }
       stage('Upload to Artifactory (configFile)'){
        steps{
            configFileProvider([configFile(fileId: 'artifactory-settings', targetLocation: 'mvn_settings_managed', variable: 'mvn_settings_managed')]) {
                sh 'mvn deploy -s $mvn_settings_managed'
            }
        }
       }
    }
}