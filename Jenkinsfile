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
                sh 'cd docker && docker build -t jiang-zuul .'
            }
        }
        stage('run') {
            steps {
                echo '==>start run'
                sh 'cd docker && docker-compose down && docker-compose up -d'
            }
        }
        stage('del') {
            steps {
                echo '==>start del'
                echo 'docker rmi $(docker images -q -f dangling=true)'
            }
        }
    }
}