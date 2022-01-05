node {
    stage('Git Clone') { 
	  git credentialsId: 'git', url: 'https://github.com/kartikeyapro/ks.git'
    }
    stage('Maven Clean') {
        sh 'mvn clean'
    }
    stage('Maven Validate') {
        sh 'mvn validate'
    }
	  stage('Sonarqube') {
        sh 'mvn sonar:sonar  -Dsonar.host.url=http://34.125.186.195:9000 -Dsonar.login=1cd1a086ad45914aac5f7a2103d43f932ae0f5d8'
    }
	 stage('Maven Compile') {
        sh 'mvn compile'
    }
	 stage('Maven Test') {
        sh 'mvn test'
    }
	 stage('Maven Package') {
        sh 'mvn package'
    }
	 stage('Maven Deploy') {
        sh 'mvn deploy'
    }
}

