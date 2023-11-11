pipeline {
    agent any

    tools {
          maven 'maven-3.9.5'
    }

    stages {
        stage('Code Clone') {
            steps {
               git credentialsId: 'git', url: 'https://github.com/ksrepo9/ks.git'
            }
			}
		stage('Maven Version') {
            steps {
               sh 'mvn --version'
            }
			}	
		stage('Maven Clean') {
            steps {
               sh 'mvn clean'
            }
			}
		stage('Maven Validate') {
            steps {
               sh 'mvn validate'
            }
			}
		stage('Sonar Scan'){
            steps {
             
			  sh 'mvn sonar:sonar -Dsonar.host.url=http://34.125.17.39:9000 -Dsonar.login=f4c15835285f8abda87d924b32e94d62e2befa76'
			 }
			 }			
			 
				stage('Maven Compile') {
            steps {
               sh 'mvn compile'
            }
			}
		stage('Maven Test') {
            steps {
               sh 'mvn test'
            }
			}
		stage('Maven Package') {
            steps {
               sh 'mvn package'
            }
			}			
		stage('Maven Deploy') {
            steps {
               sh 'mvn deploy'
            }
			}			

   }
}