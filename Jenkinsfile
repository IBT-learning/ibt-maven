pipeline {
    agent any

parameters{
    string(name:"Branch_Name", defaultvalue: "main", description: "Enter branch to build")
}
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
              git branch: '$Branch_Name', changelog: false, poll: false, url: 'https://github.com/maamejoe358/nov-cohort.git'
            }
    }
    stage('list files'){
        steps{
            echo"listing files to verify"
        bat 'dir

            }
        }

}
}