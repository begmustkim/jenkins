groovy pipeline { 
    agent any stages {
        stage('Build') { 
            
            steps { echo 'Building...'
                  }
        }
        stage('Test') {
            steps {
                echo 'Testing...'
            } 
        } 
        stage('Docker Build') {
            steps { 
                sh 'docker build -t my-app:latest .'
            }
        }
        stage('Deploy') {
            steps { 
                sh 'docker rm -f my-app-container || true' sh 'docker run -d -p 8081:80 --name my-app-container my-app:latest'
            }
        }
    }
}
