
pipeline {
    agent any

    
    stages {
        stage('Checkout') {
            steps {
                // Check out your Git repository here
                git branch: 'main', url: 'https://github.com/abdraheem98/URL-Shortner-app.git'
            }
        }
        stage('Create Virtual Environment') {
            steps {
                sh 'python3 -m venv /var/lib/jenkins/workspace/Flask-app/venv'
            }
        } 
        
        stage('Install Python Dependencies') {
            steps {
                sh '/var/lib/jenkins/workspace/Flask-app/venv/bin/pip install -r requirements.txt'
            }
        }
        stage('Run Flask App') {
            steps {
                // Run your Flask app using a Docker container
                sh 'docker run -d -p 5000:5000 my-flask-app'
            }
        }
    }
}
