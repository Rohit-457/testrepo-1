pipeline{
        agent any
		parameters {
  		string defaultValue: 'DEV', name: 'ENV'
	}
	
	triggers {
  		pollSCM '* * * * *'
	}


        stages {
                stage(checkout){
                        steps{
                                git 'https://github.com/Rohit-457/testrepo-1.git'
                        }
                }
                stage( build){
                        steps{
                        sh 'mvn install'
                        }
                }
                stage(deploy){
                        steps{
                                sh 'cp target/testrepo-1.war /home/rohit/Documents/devops/apache-tomcat-9.0.93/webapps'
                        }
                }
		stage('Deployment'){
		    	steps {
			script {
			 if ( env.ENV == 'QA' ){
        	sh 'cp target/PIPELINE.war /home/swapnil/Documents/DevOps-Software/apache-tomcat-9.0.79/webapps'
        	echo "deployment has been COMPLETED on QA!"
			 }
			else ( env.ENV == 'UAT' ){
    		sh 'cp target/PIPELINE.war /home/swapnil/Documents/DevOps-Software/apache-tomcat-9.0.79/webapps'
    		echo "deployment has been done on UAT!"
			}

        }
}}

