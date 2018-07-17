node {
   def mvnHome
   stage('Preparation') { // for display purposes
      // Get some code from a GitHub repository
      git 'https://github.com/vemular1/jenkins-maven-pipeline.git'
      // Get the Maven tool.
      // ** NOTE: This 'M3' Maven tool must be configured
      // **       in the global configuration.           
      mvnHome = tool 'M3'
   }
   stage('compile') 
      // Run the maven build
      {
         sh "'${mvnHome}/bin/mvn' -Dmaven.test.failure.ignore clean compile"
      } 
      
    stage('test') {
      // Run the maven test
         sh "'${mvnHome}/bin/mvn' -Dmaven.test.failure.ignore clean test"
         }
      
    stage('package') {
      // Run the maven package
         sh "'${mvnHome}/bin/mvn' -Dmaven.test.failure.ignore clean package"
         }
   
   stage('Results') {
      junit '**/target/surefire-reports/TEST-*.xml'
      archive 'target/*.jar'
   }
}
