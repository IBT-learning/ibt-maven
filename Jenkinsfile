pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
            }
        }
        stage('Mezanin') {
                    steps {
                        sh "pwd"
                        sh "whoami"
                        script {
                            def version = '1.2'
                            echo "${version}"
                        }
                    }
                }
        stage('Hi') {
            steps {
                echo 'Hi this is Koby'
                echo 'Let\'s see how this goes'
            }
        }
        stage('Git Checkout') {
            steps {
                echo 'additional print statement'
                echo 'Let us get together'
                echo 'Michael Jordan'
                echo 'Michael Jackson'
                echo 'Bill Clinton'
                echo 'now what'
                git branch: 'feature_koby2', changelog: false, credentialsId: 'for-github', poll: false, url: 'https://github.com/IBT-learning/ibt-maven.git'
            }
        }
    }
    post {
        always {
            echo "i will run always"
        }
    }
}
