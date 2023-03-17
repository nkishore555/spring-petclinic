pipeline {
    agent any
      triggers{
      pollSCM('* * * * *')
      }

        stages {
            stage('vcs') {
               steps{
                  git url: 'https://github.com/nkishore555/spring-petclinic.git',
                  branch: 'main'
                }
            }
        
            stage('build') {
               steps{
                  sh "mvn package"
                }
        }
            stage('sonar analysis') {
               steps{
                  withSonarQubeEnv('sonarqube') {
                  sh 'mvn clean install sonar:sonar -Dsonar.organization=kishore -Dsonar.projectKey=kishore_kumar'
                     }
                }
        }
     }
        
}
