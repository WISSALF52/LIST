pipeline {
    agent any
    environment {
        GIT_REPO = 'https://github.com/WISSALF52/LIST.git'
    }
    stages {
        stage('Clone') {
            steps {
                echo "Clonage du dépôt GitHub"
                git url: "${GIT_REPO}", branch: 'main' // Remplace par la branche correcte si nécessaire
            }
        }
        stage('Build') {
            steps {
                echo "Construction du projet avec Gradle"
                // Exécute la commande Gradle pour construire le projet
                sh './gradlew clean build'
            }
        }
        stage('Test') {
            steps {
                echo "Exécution des tests avec Gradle"
                // Exécute les tests avec Gradle
                sh './gradlew test'
            }
        }
        stage('Deploy') {
            steps {
                echo "Déploiement (si nécessaire)"
                // Ajoute ici le script de déploiement si nécessaire, sinon supprime cette étape
                // Exemple : sh './deploy.sh'
                sh 'echo "Ajoutez la commande pour le déploiement"'
            }
        }
    }
    post {
        success {
            echo "Le pipeline a réussi"
        }
        failure {
            echo "Le pipeline a échoué"
        }
    }
}
