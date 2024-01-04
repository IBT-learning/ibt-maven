pipeline {
    agent any
    parameter {
        string(name: "Branch_Name", defaultValue: "main", description: "Enter branch to build")
    }
    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
            }
        } //stage1 end
        stage('hi') {
            steps {
                echo 'Hello World'
            }
        } //stage2 end
        stage('Download from Git') {
            steps {
                git branch: '$Branch_Name', changelog: false, credentialsId: 'GITHUB_cred_alaskatubbie', poll: false, url: 'https://github.com/Alaskatubbie/nov-cohort.git'
            }
        } //stage3 end
        stage('List files') {
            steps {
                    bat 'dir'
            }
        } //stage4 end
    } //stages ending

} //Pipeline end