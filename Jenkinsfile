node ('worker_node1') { 
    def mvnHome
    mvnHome = tool 'M3'
    
    stage('Source') { // for display purposes 
        // Get some code from our Git repository 
        git 'https://github.com/dle95035/simple-java-maven-app.git'
    } 
    
    stage('Build') {
        sh "'${mvnHome}/bin/mvn' -Dmaven.test.failure.ignore clean package"
        
    }
    
    stage('Results') {
	  echo I am unit testing...
      junit '**/target/surefire-reports/TEST-*.xml'
      archive 'target/*.jar'
   }
} 