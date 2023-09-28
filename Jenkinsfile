pipeline {
    
    agent any
    
    tools {
        ant 'Ant12'
        nodejs 'Node18'
    }

    
    stages {
        
        stage('Build with Ant12') {
            steps {
                sh 'echo "Building the project..."'
                // Make sure Ant is available on the Jenkins agent
                // You can install Ant on the agent if necessary
              
            }
        }

        stage('Compile and Run Java Application') {
            steps {
                // Run your Java application
                sh 'javac testing.java'
                sh "java testing"
            }
        }
        
        stage('Test') {
            steps {
                sh 'echo "Running tests..."'
            }
        }
        stage('Deploy') {
            steps {
                sh 'echo "Deploying the application..."'
            }
        }
    }

    
    post {
        success {
            // Notify or perform actions if the build succeeds
            echo 'Build succeeded!'
        }
        failure {
            // Notify or perform actions if the build fails
            echo 'Build failed!'
        }
    }
}
