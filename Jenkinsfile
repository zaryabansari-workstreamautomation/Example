pipeline {
    
    agent any
    
    tools {
        ant 'Ant12'
        nodejs 'Node18'
    }

    environment {
        VERSION_NAME =  "1.10.13"

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
                sh 'echo "${VERSION_NAME}"'
                sh "java Example"
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
        failure {
            emailext(
                subject: "Failed: \${currentBuild.fullDisplayName}",
                body: "Build failed. Check the console output: \${BUILD_URL}",
                to: 'zaryab.ansari@workstreamautomation.com',
                attachLog: true
                )
            }
        
        success {
            emailext(
                subject: "Success: \${currentBuild.fullDisplayName}",
                body: "Build succeeded. View the details: \${BUILD_URL}",
                to: 'zaryab.ansari@workstreamautomation.com'
                )
            }

        }

    


}
