pipeline {
	agent{
	label 'slave1'
	}
	stages {
	    stage('Checkout') {
	        steps {
			checkout scm			       
		      }}
		stage('Build') {
	           steps {
			  sh 'JAVA_HOME=/home/grras/slavedir/jdk-11.0.24 /home/grras/slavedir/apache-maven-3.9.8/bin/mvn install'
	                 }}
		stage('Deployment'){
		    steps {
			sh 'cp target/Project-3.war /home/grras/slavedir/apache-tomcat-9.0.93/webapps'
			}}	
		stage('slack-notification'){
		   steps {
		     
		     slackSend baseUrl: 'https://hooks.slack.com/services/', channel: 'devops-slack', color: 'good', message: 'hello slack', teamDomain: 'Devops', tokenCredentialId: 'slack-notifer'
		     }}	
}}
