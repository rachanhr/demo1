pipeline {
	
}
	tools {
 		 maven 'm398'
		}
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
		sh 'echo test'
}
	   }
   	post {
		always {
                 archiveArtifacts artifacts: 'target/**.jar', followSymlinks: false
                 junit stdioRetention: '', testResults: 'target/surefire-report/*.xml'

    	 	}
}

    }
stage('delet') { 
deleteDir()
}
}
