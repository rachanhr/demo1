pipeline {

	agent any
		stages {
 	 stage('build') {
  	  steps {
      	    sh 'mvn install -DskipTests'
  }
}

stage('test') {
	step {
		sh 'echo rk'
	}
           post {
		always {
   		 archiveArtifacts artifacts: 'Amazon-Core/target/**.jar', followSymlinks: false
    	 	}
}

    }
  }

