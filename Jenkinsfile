pipeline {
    agent any
    stages {
        stage('mvn') {
            steps {
                echo '==>start mvn'
                sh 'mvn clean package'
            }
        }
        stage('copy') {
            steps {
                echo '==>start copy'
                sh 'cp target/jiang-zuul-1.0.0-SNAPSHOT.jar docker'
            }
        }
        stage('build') {
            steps {
                echo '==>start build'
                sh 'cd docker && ls'
            }
        }
    }
}