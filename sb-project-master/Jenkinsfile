node {
   def mvnHome
   stage('Preparation') { // for display purposes
      // Get some code from a GitHub repository
      git 'https://github.com/AlilioMaya/devops-m1-thesis.git'
      // Get the Maven tool.
      // ** NOTE: This 'M3' Maven tool must be configured
      // **       in the global configuration.           
      mvnHome = tool 'M3'
   }
   stage('test') {
         sh "cd sb-project && '${mvnHome}/bin/mvn' test"
     
   }
   stage('Build') {
      // Run the maven build
         sh "cd sb-project && '${mvnHome}/bin/mvn' -Dmaven.test.failure.ignore clean package"
   }
   stage('Build docker image') {
        sh "cd sb-project && docker build . -t 'sb-project:latest' --no-cache"   
   }
  
}
