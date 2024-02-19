pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
            }
        }
        stage('Vamsi') {
            steps {
                echo 'This is Vamsi'
            }
        }
        stage('Downloading Git Repo') {
             steps {
                 git changelog: false, credentialsId: 'GitHub_cred_vamsi', poll: false, url: 'https://github.com/VamsiKrishnaYadavLoya/demo-nov.git'
             }
        }
    }
}
