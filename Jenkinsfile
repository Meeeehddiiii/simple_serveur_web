pipeline {
    agent any
    
    stages {
        stage('Checkout') {
            steps {
                // Récupérer le code depuis GitHub
                git 'https://github.com/Meeeehddiiii/simple_serveur_web.git'
            }
        }
        
        stage('Copy Playbook from Remote Machine') {
            steps {
                script {
                    // Copier playbook.yml depuis ta VM
                    sh 'scp azureuser@10.0.0.6:/home/azureuser/playbook.yml ./'
                }
            }
        }
        
        stage('Test') {
            steps {
                script {
                    // Vérifier la syntaxe du playbook
                    sh 'ansible-playbook --syntax-check playbook.yml'
                }
            }
        }
    }
}
