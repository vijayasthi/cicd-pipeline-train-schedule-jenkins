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
                script{
                    zip archive: true, dir: '', glob: '', zipFile: 'testz.zip'
                }
            }
        }
         stage('Test') {
            steps {
                echo 'Test build automation'
            }
        }
    }
}
