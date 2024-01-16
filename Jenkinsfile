pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
            }
        }
        stage('Hi') {
            steps {
                echo 'Hi'
            }
    }
    stage('sweet') {
            steps {
                echo 'sweet'

            }
    }
    stage('download from Git'){
        steps{
              git branch: 'main', changelog: false, poll: false, url: 'https://github.com/maamejoe358/nov-cohort.git'
            }

            }
        }

}
}