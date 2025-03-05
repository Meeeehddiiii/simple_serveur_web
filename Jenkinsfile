pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Cloner le dépôt GitHub en spécifiant la branche "main"
                git branch: 'main', url: 'https://github.com/Meeeehddiiii/simple_serveur_web.git'
            }
        }

        stage('Vérification de la syntaxe HTML') {
            steps {
                // Vérification de la syntaxe du fichier index.html
                script {
                    sh 'tidy -e index.html'
                }
            }
        }
    }
}
