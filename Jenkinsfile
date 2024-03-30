pipeline {
    agent any

    stages {
        stage('Test') {
            steps {
                script {
                    // Check if Docker is available
                    bat 'docker info'
                }
            }
        }

        stage('Build') {
            steps {
                script {
                    // Build the Docker image from a Java file
                    bat 'docker build -t pythonwebapp .'
                }
            }
        }

        stage('Deploy') {
            steps {
                script {
                    // Run a container using the Docker image
                    bat 'docker run -d --name python-container pythonwebapp'
                    // Fetch the output of the java script
		    bat 'docker logs python-container'
                }
            }
        }
    }
}
