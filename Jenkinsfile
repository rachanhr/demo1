pipeline {

	agent any
	

	stages {
 	 stage('build') {
  	  steps {
      	    sh 'mvn install -DskipTests'
  }
}

stage('test') {
	steps  {
		sh 'echo r'
	   }
   	post {
		always {
                 archiveArtifacts artifacts: 'target/**.jar', followSymlinks: false
                 junit stdioRetention: '', testResults: 'target/surefire-report/*.xml'

    	 	}
}

    }
  }
}
