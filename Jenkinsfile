pipeline {
 agent any
	tools {
        maven 'mymaven' 
    }
    stage('Sonarqube') {
    environment {
        scannerHome = tool 'sonascanner'
    }
    steps {
        withSonarQubeEnv('sonarcloud') {
            sh "${scannerHome}/bin/sonar-scanner"
        }
        timeout(time: 10, unit: 'MINUTES') {
            waitForQualityGate abortPipeline: true
        }
    }
}
}
    
