pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'Running build automation'
                //sh './gradlew build --no-daemon'
                bat './gradlew.bat --no-daemon'
                //archiveArtifacts artifacts: 'dist/trainSchedule.zip'
                //archiveArtifacts artifacts: '**/*'
                //archiveArtifacts artifacts: '**/*.zip'
                bat 'mkdir -p archives'
                bat 'echo thetest > archives/testa.txt'
            }
        }
         stage('Test') {
            steps {
                echo 'Test build automation'
            }
        }
    }
}
