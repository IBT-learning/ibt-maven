pipeline{
 agent any

parameters{
    string(name: 'Branch_name', defaultValue: 'main', description: 'Enter branch to build')
    choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')
}

 stages{
    stage("hello"){
    steps{
    echo "Hello World!"
    }
   }
    stage("hi"){
        steps{
        echo "hi this is abel"
        }
    }
    stage("Github download"){
        steps{
        git branch: '$Branch_name', credentialsId: 'asulamo24_github_credentials', url: 'https://github.com/IBT-learning/ibt-maven.git'

        }
    }
    stage("List Repo contents"){
        steps{
        sh 'ls -lrt'
        }
    }
    stage('Print commands'){
    when{
        expression{
        ${params.CHOICE}=='Two'
        }
    }
    steps{
    echo '$CHOICE'
    echo "Choice: ${params.CHOICE}"
    }
    }
    stage('Example Deploy'){
      when{
        branch 'main'
      }
        steps{
            echo "Deploying... "
        }
    }

 }


}
