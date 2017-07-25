//STart The pipeline
pipeline {

	//Where The Pipeline Job Will Run
	agent any

	//Start of the stages:build, test, deploy ...
	stages {

		//Start of the Build stage
		stage('build') {
			//Start of the steps to run inside Build stage
			steps {

			//Build with Maven
			bat 'mvn clean install'
			}
		}
	}
}