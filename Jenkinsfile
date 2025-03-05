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
                    // Installer npm et htmlhint dans l'environnement
                    sh 'apt-get update && apt-get install -y npm && npm install -g htmlhint'
                    
                    // Vérifier la syntaxe du fichier index.html, en s'assurant qu'il est bien présent
                    sh 'cd simple_serveur_web && htmlhint index.html'
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
