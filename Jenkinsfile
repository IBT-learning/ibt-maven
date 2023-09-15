pipeline {
parameters {
    string(name:'Branch_name', defaultValue:'main', description:'enter your branch name')
}
    agent any
    stages {
        stage ('hello') {
            steps {
                echo "hello world"
            }
        }
         stage ('hi') {
             steps {
                  echo "hi"
             }
         }
         stage ('windows bash cmd') {
            steps {
                sh "pwd"
            }
         }
    }
}
