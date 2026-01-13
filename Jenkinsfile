pipeline {
    agent { label 'Java' }

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
                sh 'export JAVA_HOME_PATH=$(dirname $(readlink -f $(which java))))
                echo $JAVA_HOME
                sh 'export PATH=$JAVA_HOME/bin:$PATH'
                sh 'mvn clean install'
            }
        }

        stage('Deploy') {
            steps {
                sh '''
                nohup java -jar target/*.jar > app.log 2>&1 &
                '''
            }
        }
    }
}
