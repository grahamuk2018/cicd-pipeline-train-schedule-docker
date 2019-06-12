pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'Running build automation'
                sh './gradlew build --no-daemon'
                archiveArtifacts artifacts: 'dist/trainSchedule.zip'
                sh 'sudo docker build -t grahamseanking/train-schedule .'
            }
        }
    }
}
