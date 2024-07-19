pipeline {

	agent any
	parameters {
  string defaultValue: 'rachan', name: 'ame', trim: true
}


	stages {
 	 stage('build') {
  	  steps {
      	    sh 'mvn install -DskipTests'
  }
}

stage('test') {
	steps  {
		sh 'echo &name'
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
