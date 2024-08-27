pipeline{

	agent any 
	
	parameters {
  	choice choices: ['DEV', 'QA', 'UAT'], name: 'ENVIRONMENT'
	}
	triggers {
  		pollSCM '* * * * *'
	}
	stages {

		stage (checkout){
			steps{
				git 'https://github.com/devops-catchup/GRRAS1.git'
			}
		}
		stage (compilebuild){
			steps{
				sh 'mvn install'
			}
		}
		stage('Deployment'){
		    steps {
			script {
			 if ( env.ENVIRONMENT == 'QA' ){
        	sh 'cp target/CICD.war /home/swapnil/Documents/DevOps-Software/apache-tomcat-9.0.79/webapps'
        	echo "deployment has been done on QA!"
			 }
			elif ( env.ENVIRONMENT == 'UAT' ){
    		sh 'cp target/CICD.war /home/swapnil/Documents/DevOps-Software/apache-tomcat-9.0.79/webapps'
    		echo "deployment has been done on UAT!"
			}
			echo "deployment has been done!"
			fi
		}
		}
	}
}
}
