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
                sh 'ant clean compile' // Adjust the Ant targets as needed
            }
        }

        stage('Run Java Application') {
            steps {
                // Run your Java application
                sh 'java -cp test.java' // Replace with your main class and classpath
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
