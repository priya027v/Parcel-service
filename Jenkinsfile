pipeline {
    agent { label 'java_node' }

    stages {
        stage('Checkout') {
            steps {
                git branch: 'feature-1',
                    url: 'https://github.com/priya027v/Parcel-service.git'
            }
        }

        stage('Build') {
            steps {
                sh 'java -version'
                sh 'mvn -version'
                sh 'mvn clean install'
            }
        }
    }
}
