pipeline {
	agent any
	parameters {
		choice(name: 'ENVIRONMENT', choices: ['QA','UAT'], description: 'Pick Environment value')
	}
	stages {
	    stage('Checkout') {
	        steps {
			checkout scm			       
		      }}
		stage('Build') {
	           steps {
			  sh '/home/rohit/Documents/devops/apache-tomcat-9.0.93/bin/mvn install'
	                 }}
		stage('Deployment'){
		    steps {
			script {
			 if ( "${env.ENVIRONMENT}" == 'QA' ){
        	sh 'cp target/testrepo-1.war '/home/rohit/Documents/devops/apache-tomcat-9.0.93/webapps'
        	echo "deployment has been done on QA!"
			 }
			elif ( "${env.ENVIRONMENT}" == 'UAT' ){
    		sh 'cp target/testrepo-1.war '/home/rohit/Documents/devops/apache-tomcat-9.0.93/webapps'
    		echo "deployment has been done on UAT!"
			}
			echo "deployment has been done!"
			fi
			
			}}}	
}
}
