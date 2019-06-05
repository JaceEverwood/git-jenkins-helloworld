def mvnHome = 'D:\\apache-maven-3.6.0'
def pipelineFolder = 'C:\\Program Files (x86)\\Jenkins\\workspace\\scmpipeline'
def warName = 'Jacehellworld.war' //depends on maven project final Name and if the final artifact is .war
pipeline {
  agent any 
    stages {
	      
	   stage('pulling-code') {
		   steps{
			   git url: 'https://github.com/JaceEverwood/git-jenkins-helloworld.git'
		   }
	   }
	   
	   //use dir(folderLocation) if project has to be build in other folder
	   stage('building-project'){
		   steps{
			   bat "${mvnHome}\\bin\\mvn clean package "
		   }
	   }
	   
	   stage('deploy-tomcat'){
		   steps{
			   dir(pipelineFolder){
				   bat "copy .\\target\\${warName} D:\\apache-tomcat-9.0.10\\webapps"
			   }
		   }
	   }
    }
}
