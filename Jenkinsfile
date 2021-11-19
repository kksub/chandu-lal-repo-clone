node{
    def mvnHome
 
   stage('SetEnv') { 
      git 'https://github.com/kksub/chandu-lal-repo-clone.git'
      mvnHome = tool 'MAVEN_HOME'
	   
   }
   
   stage('CompileandPackage') {
      withEnv(["MVN_HOME=$mvnHome"]) {
            bat(/"%MVN_HOME%\bin\mvn" -Dmaven.test.failure.ignore clean compile/)
         }
      
   }
   stage('Snyk'){
        snykSecurity failOnIssues: false, organisation: '0c376519-722a-4aef-b7fc-f20d34e1bc2f', snykInstallation: 'subhas snyk', snykTokenId: 'snyk_key_sub'
       
   }

}
