pipeline {
	agent any
	parameters {
		choice(name: 'ENVIRONMENT', choices: ['QA','UAT'], description: 'Pick Environment value')
	}
	stages {
	    stage('Checkout') {
	        steps {
			git 'https://github.com/Rohit-457/testrepo-1.git'		       
		      }}
		stage('Build') {
	           steps {
			  sh '/mvn install'
	                 }}
}	
}

