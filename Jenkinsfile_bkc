pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'feature-1',
                    url: 'https://github.com/priya027v/Parcel-service.git'
            }
        }

        stage('Build') {
            steps {
                sh '''
                java -version
                mvn -version
                mvn clean install
                '''
            }
        }

        stage('Publish') {
            steps {
                sh '''
                mvn deploy
                '''
            }
        }
    }
}
