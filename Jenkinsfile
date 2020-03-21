pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo '==>start mvn'
                sh 'mvn clean package'
            }
        }

    }
}