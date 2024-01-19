pipeline {
    agent any

    parameters{
        string(name:"Branch_Name",defaultValue:"feature-ramin", description:"Enter branch name")
        choice(name: 'CHOICES', choices: ['one', 'two', 'three'], description: 'choose a number')
    }
    environment { 
        version = '1.1.3'
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
                sh 'ls -lrt'
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
                    env.Branch_Name == 'main'
                }
            }
            steps{
                echo "running on main branch"
            }
        } //step 6
        stage('testing after condition'){
            steps{
                echo 'testing'
                echo "${env.version}"
                sh 'echo %version%'
                script {
                    print env.version
                }
            }
        } //step 7 

    } // stages

    post { 
        always { 
            echo 'I will always say Hello again!'
        }
    }
} // End pipeline