	pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                git credentialsId: 'github-token', branch: 'main', url: 'https://github.com/Meeeehddiiii/simple_serveur_web.git'
            }
        }
        stage('Test') {
            steps {
                script {
                    sh 'ansible-playbook --syntax-check playbook.yml'
                }
            }
        }
    }
}
