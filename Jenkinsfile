#!groovy
node {
	stage('checkout'){
		checkout scm
	}
  /*  stage('checkout'){
    git credentialsId: 'bfb0bd11-3a10-406c-97d3-d7b03852b478', url: 'https://github.com/Mithuntechnologieses/maven-web-application.git'
    } */
     stage('install')
    {
        def mvn_version = 'maven'
         withEnv( ["PATH+MAVEN=${tool mvn_version}/bin"] )
	       {

          sh 'mvn clean install'
	       }
}
    stage('sonar')
    {
        def mvn_version = 'maven'
         withEnv( ["PATH+MAVEN=${tool mvn_version}/bin"] )
	       {

          sh 'mvn sonar:sonar '
	       }

    }
    stage('deploy')
    {
        def mvn_version = 'maven'
         withEnv( ["PATH+MAVEN=${tool mvn_version}/bin"] )
	       {

          sh 'mvn clean deploy'
	       }

    }
        
}
