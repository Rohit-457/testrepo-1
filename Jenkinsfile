pipeline {
	agent any 
	
	parameters {
  		string defaultValue: 'DEV', name: 'ENV'
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
			 if ( env.ENV == 'QA' ){
        	sh 'cp target/testrepo-1 /home/rohit/Documents/devops/apache-tomcat-9.0.93/webapps
        	echo "deployment has been COMPLETED on QA!"
			 }
			else ( env.ENV == 'UAT' ){
    		sh 'cp target/testrepo-1.war /home/rohit/Documents/devops/apache-tomcat-9.0.93/webapps
    		echo "deployment has been done on UAT!"
			}
			}}}	
}}
