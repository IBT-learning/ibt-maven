pipeline {
    agent any
    parameters {
        string(name:'Branch', defaultValue:'main', description:'enter branch to build')
        choice(name:'test', choices:['ice-cream', 'chocalte'], description:'choose')
    }

    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
            }
        }
         stage('hi') {
            steps {
                echo 'Hi'
            }
        }
        stage('Git checkout') {
            steps {
                echo 'Hi this is my first pipeline job'
                git branch: '${Branch}', changelog: false, credentialsId: 'for-github', poll: false, url: 'https://github.com/IBT-learning/ibt-maven.git'
            }
        }
         stage('GItSCM') {
                    steps {
                        echo 'trying gitscm to hook logs'
                        echo ${test}
                    }
                }
    }
}