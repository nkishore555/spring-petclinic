pipeline {
    agent { label 'mynode' }
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
