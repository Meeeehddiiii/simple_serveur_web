pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                // Récupérer le code depuis GitHub
                git branch: 'main', url: 'https://github.com/Meeeehddiiii/simple_serveur_web.git'
            }
        }
        stage('Copy playbook from remote machine') {
            steps {
                // Copier playbook depuis la machine distante vers Jenkins
                sh '''
                    scp azureuser@10.0.0.6:/home/azureuser/playbook.yml /var/lib/jenkins/workspace/Pipeline_serveur_web/
                '''
            }
        }
        stage('Test') {
            steps {
                script {
                    // Exécuter le test du playbook (vérification de syntaxe)
                    sh 'ansible-playbook --syntax-check playbook.yml'
                }
            }
        }
    }
}
