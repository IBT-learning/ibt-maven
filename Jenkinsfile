pipeline {
    agent any

    stages {
        stage('Git-Clone') {
            steps {
                echo 'cloning'
            }
        }
        
    stage('Validate')
         {
            steps{
                withMaven(maven: 'maven_3.8') {
                    sh "mvn validate"
                }
            }
         }
