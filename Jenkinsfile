pipeline {
    agent any

    environment {
        // Aquí defines variables de entorno si las necesitas, como el repositorio de GitHub
        GIT_URL = 'https://github.com/IvanDC03/AppGithubActionBasica2.git'
    }

    stages {
        stage('Checkout') {
            steps {
                // Aquí se hace el checkout del repositorio de GitHub
                git url: 'https://github.com/IvanDC03/AppGithubActionBasica2.git', credentialsId: 'a3600eab-6fd0-44b2-8429-2243902a69e0'
            }
        }
        
        stage('Build') {
            steps {
                sh 'npm install'
                sh 'npm run build'
                echo 'Building the project...'
                // Por ejemplo, si usas Maven:
                // sh 'mvn clean install'
            }
        }

        stage('Test') {
            steps {
                // Aquí puedes ejecutar tus pruebas
                echo 'Running tests...'
                // Por ejemplo, si usas JUnit:
                // sh 'mvn test'
            }
        }

        stage('Deploy') {
            steps {
                withCredentials([string(credentialsId: 'vercel-token', variable: 'VERCEL_TOKEN')]) {
                sh 'vercel --token $YFhmAH93eCTs5nz3iAHgkbAF --prod --yes'
                echo 'Deploying the project...'
                
            }
        }
    }

    post {
        always {
            echo 'Pipeline finished.'
        }
        success {
            echo 'Pipeline completed successfully!'
        }
        failure {
            echo 'Pipeline failed!'
        }
    }
}
}
