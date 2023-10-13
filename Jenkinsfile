pipeline {
    agent any
     string(name: 'branch_name', defaultValue: 'feature_abreham', description: 'enter the branch to build')

    stages{
        stage('Hello') {
            steps{
                echo "hello"
            }
        }
         stage('Git checkout') {
                    steps{
                        git branch: '$branch_name', credentialsId: 'mvn_user_credential_github', url: 'https://github.com/IBT-learning/ibt-maven.git'
                    }
                }
                stage('list my files'){
                    steps{
                        bat 'dir'
                    }
                }
    }
}