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
	step {
		sh 'echo &name'
	}
           post {
		always {
   		 archiveArtifacts artifacts: 'Amazon-Core/target/**.jar', followSymlinks: false
    	 	}
}

    }
  }

