pipeline {
    agent any
 parameters{
 string(name: 'Branch_Name', defaultValue:'main',description: 'Enter the branch to build')
        stage('Hello') {
            steps {
                echo 'Hello World'
            }
        }
        stage('firstline') {
            steps{
                echo 'We are testing maven pipeline job'
            }
        }

    }
}