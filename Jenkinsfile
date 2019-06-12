pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'Running build automation'
                sh './gradlew build --no-daemon'
                archiveArtifacts artifacts: 'dist/trainSchedule.zip'
            }
        }
        stage('deploy') {
            steps {
                sh 'docker build -t grahamseanking/train-schedule .'
                sh 'docker run -p 8080:8081 -d grahamseanking/train-schedule'
            }
        }
    }
}
