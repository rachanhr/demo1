pipeline {
	agent any
	triggers {
  cron '* * * * *'
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
		withCredentials([usernameColonPassword(credentialsId: 'adca75dd-93e6-49c2-83de-86de3d854b6d', variable: 'login')]) {
   sh 'docker login'
}
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
