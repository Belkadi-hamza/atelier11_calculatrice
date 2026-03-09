pipeline {
    agent any
    
    tools {
        nodejs 'NodeJS-24'
    }
    
    stages {
        stage('Checkout') {
            steps {
                echo 'Récupération du code depuis GitHub...'
                checkout scm
            }
        }
        
        stage('Install dependencies') {
            steps {
                echo 'Installation des dépendances...'
                sh 'npm install'
            }
        }
        
        stage('Run tests') {
            steps {
                echo 'Exécution des tests...'
                sh 'npm test'
            }
        }
        
        stage('Build') {
            steps {
                echo 'Build de l\'application...'
                sh 'echo "Build terminé avec succès"'
            }
        }
    }
    
    post {
        success {
            echo 'Bravo, déploiement réussi !'
        }
        failure {
            echo 'Le build a échoué. Vérifiez les logs.'
        }
    }
}
