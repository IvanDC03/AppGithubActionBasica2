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
                git url: "https://github.com/IvanDC03/AppGithubActionBasica2.git", credentialsId: ''
            }
        }
        
        stage('Build') {
            steps {
                // Aquí puedes agregar el comando de compilación de tu proyecto
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
                // Aquí agregas el comando de despliegue
                echo 'Deploying the project...'
                // Por ejemplo, si usas Docker:
                // sh 'docker-compose up -d'
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
