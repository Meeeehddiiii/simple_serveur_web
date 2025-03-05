pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Récupérer le code depuis GitHub
                git 'https://github.com/Meeeehddiiii/simple_serveur_web.git'
            }
        }

        stage('Test') {
            steps {
                // Exécuter un test simple sur le playbook
                script {
                    sh 'ansible-playbook --syntax-check playbook.yml'
                }
            }
        }
    }
}
a
