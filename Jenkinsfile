//STart The pipeline
pipeline {

	//Where The Pipeline Job Will Run
	agent {
		
		label "Windows_Slave_01"
	}

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
		
		stage('deploy') {
			
			// Define the Steps
			steps {
				
				//Stop the Tomcat Service
				bat 'sc stop Tomcat7'
				bat 'ping 127.0.0.1 -n 6'
				
				//Copy The .war file from the Build target folder to the webapp Tomcat folder
				bat 'xcopy /y "C:\\temp\\CICD Setup\\Jenkins_Slave\\workspace\\GOL_Pipeline\\gameoflife-web\\target\\gameoflife.war" "C:\\temp\\CICD Setup\\Tomcat 7.0\\webapps"'
				
				//Start The Tomcat Service
				bat 'sc start Tomcat7'
			}
		}
	}
}
