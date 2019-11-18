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
			//def file = new File( 'dist/train-schedule1.zip' )
			def file = findFiles(glob: 'dist/*.zip')
				if( file.exists() ) {
					bat 'rm dist/*.zip'
				} else {
                			println "File doesn't exist and good to go"
						}
                }
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
