pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
            }
        }
        stage('Yello') {
            steps {
                echo 'Hello World'
            } //steps
        } //stage
        stage("Download from git"){
           steps{
git branch: 'main', changelog: false, credentialsId: 'Github_crnd_benny', poll: false, url: 'https://github.com/bennydelight/november-cohot.git'
           }
        }
    } //stages
} //pipeline
