pipeline {
agent any
    stages{
        stage('checkout git'){
            steps{
                git branch: 'main', credentialsId: 'git', url: 'https://github.com/dotsenkois/elk_role'
            }
        stage("install roles"){
            steps{
                sh 'ansible-galaxy role install -r requirements.yml'
            }
        }
        stage('run molecule'){
            steps{
                sh 'molecule test'
                
            }
        }
    }
}
}