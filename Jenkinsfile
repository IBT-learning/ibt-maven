pipeline {
    agent any

    parameters {
       string(name: 'Branch_name', defaultValue: 'main', description: 'Enter branch to build')
       choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')
    }

environment {
    version = '1.1.1'
}

    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
            } // step
        } // stage1
        stage('Hi') {
            steps {
                echo 'Hi this is Kingsley'
            } // step
        }// stage2
        stage('Github download') {
            steps {
                git branch: '$Branch_name', credentialsId: 'kingsley_github_credentials', url: 'https://github.com/IBT-learning/ibt-maven.git'
            }

        } //stage3
        stage ('List Repo contents') {
            steps {
                sh 'ls -lrt'
            } //step

        } //stage4
        stage ('Print commands') {
            when {
                expression {
                    '${params.CHOICE}'== 'Two'
                }
            }
            steps {
                echo '$CHOICE'
                echo "Choice: ${params.CHOICE}"
            }// step
        }// stage5
        stage ('Example Deploy') {
            when {
                branch 'main'
            }
            steps {
                echo "Deploying..."
            }// step

        }// stage6

        stage('using vars'){
            steps {
                echo '$version'
                echo "${env.version}"
                script {
                    print env.version
                }

            } // step
        } //stage7

    stage('script block') {
        steps{
            script {
                    def browsers = ['chrome', 'firefox']
                    for (int i = 0; i < browsers.size(); ++i) {
                        echo "Testing the ${browsers[i]} browser"
                    }
                }
        }// step
    }// stage8
    } // end of stages

    post { 
        always { 
            echo 'I will always say Hello again!'
        }
    }
} // end of pipeline
