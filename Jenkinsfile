pipeline{
    agent any

    tools{
        maven 'maven_3.8'
        }

        stages{
            stage('Git checkout'){
                steps{
                    git branch: 'feature_joseph', changelog: false, credentialsId: 'ibt', poll: false, url: 'https://github.com/IBT-learning/ibt-maven.git'
                        }
                    }
                    stage('Validate'){
                        steps{
                            withMaven(maven: 'maven_3.8.6') {


                        }