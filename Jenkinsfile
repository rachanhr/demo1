ipeline {

	agent any
	tools {
 		 maven 'm398'
		}

	stages {
 	 stage('build') {
  	  steps {
      	    sh 'mvn install -DskipTests'
  }
}

stage('test') {
           post {
		
   		 archiveArtifacts artifacts: 'Amazon-Core/target/**.jar', followSymlinks: false
    	 	}
}

    }
  }

