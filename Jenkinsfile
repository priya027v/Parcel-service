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
                sh '''
                    java -version
                    mvn -version

                    export JAVA_HOME=$(dirname $(dirname $(readlink -f $(which java))))
                    export PATH=$JAVA_HOME/bin:$PATH

                    echo "JAVA_HOME=$JAVA_HOME"
                    echo "PATH=$PATH"

                    mvn clean install
                '''
            }
        }

        stage('Deploy') {
            steps {
                sh '''
                    mvn spring-boot:run
                '''
            }
        }
    }
}

