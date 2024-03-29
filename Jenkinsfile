pipeline {
    agent any

    stages {
        stage('Test') {
            steps {
                script {
                    // Check if Docker is available
                    sh 'sudo docker info'
                }
            }
        }

        stage('Build') {
            steps {
                script {
                    // Build the Docker image from a Java file
                    sh 'docker build -t my-java-app .'
                }
            }
        }

        stage('Deploy') {
            steps {
                script {
                    // Run a container using the Docker image
                    sh 'docker run -d --name myapp my-java-app'
                    // Fetch the output of the java script
		    sh 'docker logs myapp'
                }
            }
        }
    }
}
