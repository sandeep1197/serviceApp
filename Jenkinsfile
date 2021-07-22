pipeline {
 agent any
  tools {
    maven 'Maven3.81'
	jdk 'MyJava'
	git 'Default'
  }
  options {
    timestamps()
    properties([buildDiscarder(logRotator(artifactDaysToKeepStr: '', artifactNumToKeepStr: '', daysToKeepStr: '5', numToKeepStr: '5'))])
 }
  stages {
    stage ('Jenkins path') {
	 steps {
	   sh '''
	   echo "This is the Jenkins Path"
	   echo "PATH=${PATH}"
	     '''
	   }
	}
	 stage ('checkout scm') {
	   steps {
	     checkout([$class: 'GitSCM', branches: [[name: '*/master']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/sandeep1197/serviceApp.git']]])
		 }
    }
     stage ('build') {
       steps {
	      sh 'mvn clean complile install' 
		 }
	}
 }
}

		
	
		
