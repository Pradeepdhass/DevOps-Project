pipeline {
    agent any

    stages {

        stage('Clone Repository') {
            steps {
                git 'https://github.com/Pradeepdhass/DevOps-Project.git'
            }
        }

        stage('Build') {
            steps {
                echo "Building Application..."
            }
        }

        stage('Test') {
            steps {
                echo "Running Tests..."
            }
        }

        stage('Deploy') {
            steps {
                echo "Deploying Application..."
                sh 'cp -r * /var/www/html/'
            }
        }
    }
}