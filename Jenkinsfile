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
                // Vérification de la syntaxe du fichier index.html avec suppression de l'échec en cas d'avertissement
                script {
                    def status = sh(script: 'tidy -e index.html', returnStatus: true)
                    if (status != 0) {
                        echo "Des avertissements ont été trouvés dans le fichier HTML."
                    } else {
                        echo "Aucun problème de syntaxe trouvé dans le fichier HTML."
                    }
                }
            }
        }
    }
}
