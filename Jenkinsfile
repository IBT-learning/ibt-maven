pipeline{
    agent any

    stages {
    stage('Git checkout') {
                steps {
                    checkout changelog: false, poll: false, scm: [$class: 'GitSCM', branches: [[name: '*/feature_nnamdi']], extensions: [], userRemoteConfigs: [[credentialsId: 'ibt', url: 'https://github.com/IBT-learning/ibt-maven.git']]]
                }
            }
    }
}
