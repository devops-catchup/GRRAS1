pipeline {
	agent{
	label 'slave-label'
	}
	stages {
	    stage('Checkout') {
	        steps {
			checkout scm			       
		      }}
		stage('Build') {
	           steps {
			  sh '/home/grras/slavedir/apache-maven-3.9.4/bin/mvn install'
	                 }}
		stage('Deployment'){
		    steps {
			sh 'cp target/GRRAS1.war /home/grras/slavedir/apache-tomcat-9.0.79/webapps'
			}}	
}}
