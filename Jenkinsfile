pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Récupérer le code depuis GitHub
                git 'https://github.com/Meeeehddiiii/simple_serveur_web.git'
            }
        }

        stage('Vérification de la syntaxe') {
            steps {
                script {
                    // Vérifier la syntaxe du fichier index.html avec un outil comme `htmlhint`
                    sh 'apt-get update && apt-get install -y npm && npm install -g htmlhint'
                    sh 'htmlhint index.html'
                }
            }
        }
    }

    post {
        success {
            echo 'La syntaxe de index.html est correcte !'
        }

        failure {
            echo 'Erreur de syntaxe dans index.html.'
        }
    }
}
