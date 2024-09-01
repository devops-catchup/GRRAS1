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
			  sh 'mvn install'
	                 }}
		stage('Deployment'){
		    steps {
			sh 'cp target/GRRAS1.war /home/swapnil/Documents/DevOps-Software/apache-tomcat-9.0.79/webapps'
			}}
		stage('slack-notification'){
		   steps {
		     
		     slackSend baseUrl: 'https://hooks.slack.com/services/', channel: '# devops-notification', color: 'good', message: 'welcome to jenkins slack world', teamDomain: 'devops', tokenCredentialId: 'slacknotifier'
		     }}		
}}
