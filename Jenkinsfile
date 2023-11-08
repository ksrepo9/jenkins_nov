node {
stage('Git Clone') {
    git credentialsId: 'git', url: 'https://github.com/ksrepo9/ks.git'      
}
   stage('mvn version') {
   sh 'mvn --version'         
}
stage('mvn validate') {
   sh 'mvn validate'         
}
stage('mvn compile') {
   sh 'mvn compile'         
}
stage('mvn test') {
   sh 'mvn test'         
}
stage('mvn package') {
   sh 'mvn package'         
}

stage('mvn deploy') {
   sh 'mvn deploy'         
}
}
