pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'Running build automation'
                //sh './gradlew build --no-daemon'
		//dir('dist') {deleteDir()}
		script{
			def zipdirexists = 'dist/train-schedule1_master.zip'
			if (zipdirexists) {
				dir('dist') {deleteDir()}
			} //else {
				//echo "Dir and File doesn't exist, new ones will be created"
				//}
			}
                bat './gradlew.bat --no-daemon --warning-mode all'
                //archiveArtifacts artifacts: 'dist/train-schedule1_master.zip'
                script{
                    //zip archive: true, dir: 'train-schedule1_master', glob: '', zipFile: 'nameOfFile'
			zip zipFile: 'dist/train-schedule1.zip', archive: true, glob: '', dir: ''
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
	    post {
        success {
            echo 'I succeeeded!'
	    echo "Succeeded Pipeline: ${currentBuild.fullDisplayName}"
            echo "${env.BUILD_URL}"
        }
        failure {
            echo 'I failed :('
	    echo "Failed Pipeline: ${currentBuild.fullDisplayName}"
            echo "${env.BUILD_URL}"
        }
    }
}
