pipeline {
	
	agent any
	parameters {
  string defaultValue: 'rk', name: 'name', trim: true
}

	stages {
 	 stage('build') {
  	  steps {
      	    sh 'mvn install -DskipTests'
  }
}
	stage('test') {
	steps  {
		withCredentials([usernameColonPassword(credentialsId: 'a696f21b-fc83-4df4-b628-62cf3f09710e', variable: 'login')]) {
    sh 'docker login'
}
}
	      	post {

		always  {
			archiveArtifacts artifacts: 'target/**.jar', followSymlinks: false
                        junit stdioRetention: '', testResults: 'target/surefire-report/*.xml'

    	 	}
	}
	}
	}
}
