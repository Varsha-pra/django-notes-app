pipeline {
    agent any

    stages {
        stage('Code') {
            steps {
               echo "This is cloning the code"  
               git url: "https://github.com/Varsha-pra/django-notes-app.git", branch: "main"
               echo "code clonned successfully"
            }
        }
        stage('Build') {
            steps {
               echo "This is building the code" 
               sh "whoami"
               sh "docker build -t notes-app:latest ."
            }
        }
        stage('Test') {
            steps {
                echo "This is testing the code" 
            }
        }
        stage('Deploy') {
            steps {
                echo "This is deploying the code" 
                sh "docker run -d -p 8000:8000 notes-app:latest"
            }
        }
    }
}
