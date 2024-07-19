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
		withCredentials([usernameColonPassword(credentialsId: 'adca75dd-93e6-49c2-83de-86de3d854b6d', variable: 'login')]) { 

sh 'dcoker login'
}
	}
           post {
		always {
   		 archiveArtifacts artifacts: 'Amazon-Core/target/**.jar', followSymlinks: false
    	 	}
}

    }
  }
}
