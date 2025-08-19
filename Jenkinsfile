pipline {
    agent any

    stages {
        stages('Clone Code'){
            stages {
                git branch: 'main', url:'https://github.com/arjun7976/CI-CD-pipeline-with-jenkins-docker.git'
            }
        }
        stages('Build Docker Image') {
            steps {
                sh 'docker build -t my-flask-app:latest .'
            }
        }
        stages('Run Container') {
            steps {
                sh '''
                docker stop flask-app || true 
                docker rm flask-app || true
                docker run -d --name flask-app -p 5000:5000 
                flask-cicd:latest
                '''
            }

        }
    }
}