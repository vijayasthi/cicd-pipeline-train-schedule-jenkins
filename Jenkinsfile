pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'Running build automation'
                //sh './gradlew build --no-daemon'
                bat './gradle.bat build'
                archiveArtifacts artifacts: 'dist/trainSchedule.zip'
            }
        }
         stage('Test') {
            steps {
                echo 'Test build automation'
            }
        }
    }
}
