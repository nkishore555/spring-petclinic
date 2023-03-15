pipeline {
    agent { label 'ansible' }
    triggers { 
        pollSCM('* * * * *')
    }
    stages {
        stage('vcs') {
            steps {
                git url: 'https://github.com/nkishore555/spring-petclinic.git',
                    branch: 'main'
            }
        }
        stage('build') {
            steps {
                sh "ansible-playbook -i hosts spring.yml"
            }
        }
    }

}
