pipeline {
    agent any
    tools{
        maven 'maven_3.8'
    }
    stages {
        stage("Checkout the project") {
            steps {
                git branch: 'master', url: 'https://github.com/IBT-learning/hello-maven.git'
            }
            }
        
        stage ("Validate the source code") {
            steps {
                sh 'mvn validate'
            }
        }
        
        stage ("Compile the source code") {
            steps {
                sh 'mvn compile'
            }
        }
       
         stage('Sonarqube scan') {
                             environment {
                                            scannerHome = tool 'ibt-sonarqube';
                             }
                             steps {
                                sh 'echo performing sonar scan'
                                withSonarQubeEnv(credentialsId: 'SQ-student', installationName: 'IBT sonarqube') {
                                    sh "${scannerHome}/bin/sonar-scanner"
                                }
                             }


        stage ("Build the package") {
            steps {
                sh 'mvn clean package'
        }
        }
    }
}

