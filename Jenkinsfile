pipeline {
	agent any

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
        steps{
            git branch: 'main', changelog: false, credentialsId: 'git_password', poll: false, url: 'https://github.com/IBT-learning/ibt-maven.git'
        }
   }
   stage('list files') {
    steps{
       //windows bat 'dir'
        sh 'ls -lrt'   //mac-unix
    }
   }
	}
}