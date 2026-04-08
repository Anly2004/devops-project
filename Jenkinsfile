pipeline {
    agent any

    stages {
        stage('Clone') {
            steps {
                git branch: 'main', url: 'https://github.com/Anly2004/devops-project.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t devops-project .'
            }
        }

        stage('Run Container') {
            steps {
		sh '''
                docker stop mycontainer || true
	        docker rm mycontainer || true
                docker run -d -p 8081:80 --name mycontainer devops-project
                '''           
            }
        }
    }
}
