pipeline {
    agent any

    parameters {
        string(name: 'BRANCH_NAME', defaultValue: 'staging', description: 'Which branch to build on')
        choice(name: 'CHOICES', choices: ['one', 'two', 'three'], description: 'Choose your number')
    }

    environment {
        version = '3.1'
        db_name = 'sql'
    }

    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
            }
        }
        stage('Hi') {
            steps {
                echo 'Hi, this is Chinwe'
            }
        }
        stage('Trying Jenkinsfile') {
            steps {
                echo 'This is running from GitHub'
                echo "DB Version: ${env.version}"
                echo "DB Name: ${env.db_name}"
                echo "App Version: ${version}"
            }
        }
        stage('Git Checkout') {
            steps {
                git branch: "${BRANCH_NAME}", changelog: false, credentialsId: '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', poll: false, url: 'https://github.com/IBT-learning/ibt-maven.git'
            }
        }

        stage('List Files') {
            steps {
                sh '''
                ls -lrt
                pwd
                who
                '''
            }
        }

        stage('Parameter') {
            when {
                expression {
                    env.BRANCH_NAME == 'main'
                }
            }
            steps {
                echo "CHOICES: ${CHOICES}"
            }
        }

        stage('Env Variable') {
            environment {
                db_version = '5.6'
            }
            steps {
                echo "DB Version: ${env.db_version}"
                sh 'echo $db_version'
                script {
                    echo env.db_version
                }
            }
        }
    }
    post{
        always{
            echo 'i will run always and say hello'
        }
    }
}