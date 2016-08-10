node {
   // Mark the code checkout 'stage'....
   stage 'Checkout'

   // Get some code from a GitHub repository
   git credentialsId: '2e9e6a89-acae-4e34-8082-d55cf93a607d', url: 'https://github.com/asarathi/spring-boot-hello.git'

   // Get the maven tool.
   // ** NOTE: This 'M3' maven tool must be configured
   // **       in the global configuration.           
   def mvnHome = tool 'M3'

   // Mark the code build 'stage'....
   stage 'Test'
   // Run the maven build
   sh "${mvnHome}/bin/mvn clean test"
   
   stage 'Package'
   sh "${mvnHome}/bin/mvn clean compile package"
}