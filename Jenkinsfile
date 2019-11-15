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
                bat 'mkdir -p archive'
                bat 'echo thetest > archive/test.txt'
                //archiveArtifacts archive: '**/*'
                //script{
                //    zip archive: true, dir: 'archive', glob: '', zipFile: 'coverage-files.zip'
                //}
            }
        }
         stage('Test') {
            steps {
                echo 'Test build automation'
            }
        }
    }
}
