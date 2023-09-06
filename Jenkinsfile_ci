@Library('jenkins-library')_
pipeline {
    agent any

    stages{

    stage('Git Checkout'){
        steps{
            echo "git checkout"
            git branch: 'feature_gunjvm', changelog: false, credentialsId: 'ibt', poll: false, url: 'https://github.com/IBT-learning/ibt-maven.git'
        }
    }
    stage('Validate') {
        steps{
           withMaven(maven: 'maven_3.8') {
              sh  'mvn validate'
           }
        }
        }
         stage('Compile') {
                steps{
                   withMaven(maven: 'maven_3.8') {
                      sh  'mvn compile'
                   }
                }
                }
         stage('SonarQube Analysis') {
            environment {
                sonarScan = tool 'ibt-sonarqube'
            }
            steps {
             withSonarQubeEnv(credentialsId: 'student-sonar-token', installationName: 'IBT sonarqube') {
               // sh "${mvn}/bin/mvn clean verify sonar:sonar -Dsonar.projectKey=July_cohort"
               sh "${env.sonarScan}/bin/sonar-scanner"
             }
            }
           }
         stage('SonarScan - Library'){
            steps{
                sonarScan()
            }
         }
        stage('Package') {
               steps{
                  withMaven(maven: 'maven_3.8') {
                     sh  'mvn package'
                  }
               }
               }
         stage('Vulnerability scan - Dependency Check')
                         {
                            steps{
                                 dependencyCheck additionalArguments: '''
                                                                            -o "./"
                                                                             -s "./"
                                                                             -f "ALL"
                                                                             --prettyPrint ''', odcInstallation: 'dependency-check'
                                         dependencyCheckPublisher pattern: 'dependency-check-report.xml'
                              }
                         }
         stage('deploy'){
            steps{
              withMaven(maven: 'maven_3.8') {
               withCredentials([file(credentialsId: 'mvn_settings_gunjan', variable: 'mvn_settings_gunjan')]) {
                   sh  'mvn deploy -s $mvn_settings_gunjan'
               }
                }
            }
         }
         stage('deploy using configFile') {
            steps{
                withMaven(maven: 'maven_3.8') {
                    configFileProvider([configFile(fileId: 'artifactory-settings', variable: 'mvn_settings_managed')]) {
                        sh 'mvn deploy -s $mvn_settings_managed'
                }
               }
            }

         }
         stage('Deploy to Dev') {
            steps{
                script{
                    def remote = [name: 'dev', host: '137.184.172.92', allowAnyHosts: true]
                    withCredentials([usernamePassword(credentialsId: 'server-ssh-pw', passwordVariable: 'password', usernameVariable: 'username')]) {
                        remote.user = username
                        remote.password = password
                        sshPut remote: remote, from: 'target/ibt-maven-1.4-SNAPSHOT.jar' , into: '/opt/tomcat/apps'
                    }
                 }
             }
         }
    }
}
