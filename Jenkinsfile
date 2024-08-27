pipeline{
        agent any
		parameters {
 			 choice choices: ['DEV', 'QA', 'UAT'], description: 'pick up', name: 'ENVIRONMENT'
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
        }
}

