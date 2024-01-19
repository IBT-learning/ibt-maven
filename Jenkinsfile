pipeline {
    agent any

    parameters{
        string(name:"Branch_Name",defaultValue:"feature-ramin", description:"Enter branch name")
    }

    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
            }
        } //stage 1
        stage('Hi') {
            steps {
                echo 'Hi World'
            }
        } //stage 2
        stage('download from git'){
            steps{
                git branch: '$Branch_Name', credentialsId: 'Github_Cred_Ramin', url: 'https://github.com/IBT-learning/ibt-maven.git'
            }
        } //stage 3
        stage('list file'){
            steps{
                echo "listing files to verify"
                bat 'dir'
            }    
        } //step 4

    } // stages
} // End pipeline