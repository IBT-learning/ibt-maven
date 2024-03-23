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
    stage('hello') {
        steps {
            echo "hello world"
        } //step
    } //stage1
    stage('hi') {
        steps {
            echo "hi this is shiney"
        } //step
    } //stage2
    stage('Github download') {
        steps{
            git branch: '$Branch_name', credentialsId: 'shiney495_github_credentials', url: 'https://github.com/IBT-learning/ibt-maven.git'
        }
    } //stage3
    stage ('List Repo contents ') {
        steps{
            sh 'ls'

        } //step
    } //stage4
    stage ('Print commands') {
    when {
        expression {
            '${params.CHOICE}'=='Two'
        }
    }
        steps {
            echo '$CHOICE'
            echo "Choice: ${params.CHOICE}"
        }
    } //stage 5
    stage ('Example Deploy'){
      when {
        branch 'main'
      }
        steps{
            echo "Deploying... "
        }
    }
    stage('using vars'){
        steps{
            echo '$version'
            echo "${env.version}"
            script {
                print env.version
            }
        }
    }
     stage('script block'){
         steps{
               script {
                                 def browsers = ['chrome', 'firefox']
                                 for (int i = 0; i < browsers.size(); ++i) {
                                     echo "Testing the ${browsers[i]} browser"
                                 }
                             }
         }
     }
     stage('webhook test'){
        steps{
            echo "yes run git scm commit hook poll"
        }
     }

 } // end of stages
 post {
        always {
            echo ' I will always say Hi!'
        }
 }
} // end of pipeline