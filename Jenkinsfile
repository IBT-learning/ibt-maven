pipeline {
	agent {label 'UX_IBT'}

    environment {
        version = "1.5"
        db_name = "ibt_db"
    }

    parameters {
        choice(name: 'CHOICES', choices: ['one', 'two', 'three'], description: '')
        string(name: 'Branch_Name', defaultValue: 'main', description:'enter branch to build')
     }

	stages{
		stage('Hello') {
		  steps {
			echo 'hello world'
		}
	}
     stage('hi') {
	steps{
		echo 'hi'
	}
  }
     stage('howdy') {
  	steps{
  		echo 'howdy'
  	}
    }
   stage('git checkout') {
       when {
        expression {
               env.BRANCH_NAME=='main'
         }
       }
        steps{
            git branch: '$Branch_Name', changelog: false, credentialsId: 'git_password', poll: false, url: 'https://github.com/IBT-learning/ibt-maven.git'
        }
   }
   stage('list files') {
    steps{
       //windows bat 'dir'
        sh 'ls -lrt'   //mac-unix
    }
   }
   stage('env variables') {
    steps{
        sh 'echo $version '
        echo "${env.version}"
        echo "${env.db_name}"

        script {
            print env.version
        }
    }
   }
   stage('test githook') {
    steps{
        echo "git hook worked automatically"
    }
   }
	}
	post {
	    always{
	        emailext body: 'Test', subject: 'Test', to: 'gunjanvm@gmail.com'
	    }
	}
}