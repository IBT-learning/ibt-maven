pipeline{
	agent any

	environment{
	    version = '1.7.3'
	    db_name = 'Ibt_db'
	    Author = 'Mr_Dromor'
	}
    parameters{
        string (name: 'Mose_app', defaultValue: 'master', description: 'Enter the Build Branch')
    }
	stages{
		stage('HELLO'){
			steps{
			echo "hello world"
			}

		}
		stage('BUILD'){
		    steps{
		        echo "Putting it all together"
		    }
		}
		stage ('STAGING'){
		    steps{
		        echo "Final Testing"
		    }
		}
		stage ('PRODUCTION'){
			steps{
			echo "We are live"
			}
		}
        stage('git checkout'){
            steps{
                git changelog: false, credentialsId: 'Git_update', poll: false, url: 'https://github.com/MDromor/maven_process.git'
            }
        }

        stage('List File'){
            steps{
                sh 'ls -lrt'
            }
        }
        stage('env variable'){
            steps{
                sh 'echo $version'
               echo '${env.db_name}'
               echo '${env.version}'
               script{
               print env.version
               print env.db_name
               }
                sh 'echo $Author'
            }
        }
	}
    post{
        always{
        echo "THIS IS THE RESULT OF YOUR RUN."
        }
    }

}