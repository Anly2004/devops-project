pipeline {
    agent any

    stages {
        stage('Clone') {
            steps {
                git 'https://github.com/Anly2004/devops-project.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t devops-project .'
            }
        }

        stage('Run Container') {
            steps {
                sh 'docker run -d -p 8081:80 devops-project'
            }
        }
    }
}
