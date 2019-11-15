pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'Running build automation'
                //sh './gradlew build --no-daemon'
                bat './gradlew.bat --no-daemon'
                //archiveArtifacts artifacts: 'dist/train-schedule1_master.zip'
                script{
                    zip zipFile: 'dist/trainSchedule'
                    archiveArtifacts artifacts: 'trainSchedule.zip'
                    }
                //script{
                //    zip archive: true, dir: '', glob: '', zipFile: 'trainSchedule.zip'
                //}
                //archiveArtifacts artifacts: 'trainSchedule.zip'
                //archiveArtifacts artifacts: 'trainSchedule1.zip'
                //archiveArtifacts(artifacts: 'dist/*')
                //archiveArtifacts(artifacts: 'dist/*.zip', fingerprint: true) 
                //archiveArtifacts artifacts: '**/*'
                //archiveArtifacts artifacts: '**/*.zip'
                //script{
                    //zip archive: true, dir: '', glob: '', zipFile: 'testz.zip'
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
