pipeline {
    agent any

    parameters{
        string(name:"Branch_Name",defaultValue:"feature-ramin", description:"Enter branch name")
        choice(name: 'CHOICES', choices: ['one', 'two', 'three'], description: 'choose a number')
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
        stage('list choice'){
            steps{
                echo "Choice: ${params.CHOICES}"
            }    
        } //step 5
        stage('run on condition'){
            when {
                expression { 
                    ${params.Branch_Name}=='main'
                }
            }
            steps{
                echo "running on main branch"
            }
        } //step 6

    } // stages
} // End pipeline