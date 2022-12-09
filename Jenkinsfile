pipeline {
 agent any
	tools {
        maven 'maven' 
    }
	 stages {
    stage('Analysis') {
	 steps {
              withSonarQubeEnv('sonarcloud') {
                sh 'mvn  sonar:sonar'
              }
              echo "Analysis going"
            }
	 }
	//  stage("Quality Gate") {
        //    steps {
         //     timeout(time: 5, unit: 'MINUTES') {
         //       waitForQualityGate abortPipeline: true
        //      }
       //       echo "quality passed"
      //      }
      //    }
}
}
    
