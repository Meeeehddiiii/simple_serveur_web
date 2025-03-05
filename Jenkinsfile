pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/Meeeehddiiii/simple_serveur_web.git'
            }
        }
        stage('Run playbook on remote') {
            steps {
                script {
                    // Exécuter le playbook sur la machine distante
                    sh '''
                        ansible-playbook -i <ip_address>, /home/azureuser/playbook.yml
                    '''
                }
            }
        }
    }
}
