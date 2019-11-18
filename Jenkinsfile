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
                    //zip archive: true, dir: 'train-schedule1_master', glob: '', zipFile: 'nameOfFile'
			zip zipFile: 'dist/nameOfFile', archive: true, glob: '', dir: ''
                }
                //archiveArtifacts artifacts: '**/*'
            }
		}
        stage('Test') {
            steps {
                echo 'Test build automation'
			}
		}
	}
}
