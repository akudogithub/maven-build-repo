pipeline{
	agent any 
	tools{
	maven 'maven'
	}
	stages{
		stage('1-version-control'){
			steps{
				checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[credentialsId: 'Github-id', url: 'https://github.com/akudogithub/maven-build-repo.git']]])
			}
		}
		stage('2-cleanws'){
			steps{
				sh 'mvn clean'
			}
		}
		stage('3-maven-build'){
			steps{
				sh 'mvn package'
			}
		}
	}
}
