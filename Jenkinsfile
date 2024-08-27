pipeline{

	agent any 
	
	triggers {
  		pollSCM '* * * * *'
	}
	stages {

		stage (checkout){
			steps{
				git 'https://github.com/devops-catchup/GRRAS1.git'
			}
		}
		stage (compile&build){
			steps{
				sh 'mvn install'
			}
		}
		stage (deploy){
			steps{
			sh 'cp target/GRRAS1.war /home/swapnil/Documents/DevOps-Software/apache-tomcat-9.0.79/webapps'
		}
		}
	}
}
