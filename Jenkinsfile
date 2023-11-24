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
             stage('Sonar Scan')
		{
		  steps {
		  sh 'mvn sonar:sonar -Dsonar.host.url=http://3.85.227.113:9000 -Dsonar.login=9047b7a58b273a59b70799eabd48f0b23b9fc7dd'
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
