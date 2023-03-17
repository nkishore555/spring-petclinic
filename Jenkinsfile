pipeline {
    agent{label 'mynode'}
    triggers{
        pollSCM('* * * * *')
    }
     stages{
        stage('vcs') {
            steps {
                git url: 'https://github.com/nkishore555/spring-petclinic.git',
                    branch: 'main'
            }
        }
        stage('Build') {
            steps {
                sh 'docker image build -t kishorekrrish/spring-petclinic:3.0 .'
                sh 'docker push kishorekrrish/spring-petclinic:3.0' 
                 }
        } 
        stage('deploy') {
           steps {
              sh 'kubectl apply -f ./k8s/spc.yaml'
           }
        }
     }
}
