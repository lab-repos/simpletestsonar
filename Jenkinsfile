pipeline{
    agent any
    environment {
        PATH = "$PATH:C:\Users\Dare Omotosho\Documents\Documents\Setups\apache-maven-3.8.6-bin\apache-maven-3.8.6"
    }
    stages{
       stage('GetCode'){
            steps{
                git 'https://github.com/lab-repos/valaxysonarQualityGateTest.git'
            }
         }        
       stage('Build'){
            steps{
                // sh 'mvn clean package'
                echo building
            }
         }
       stage('SonarQube analysis') {
//    def scannerHome = tool 'Sonarqube-Scanner'; Disabled because we are installing automatically with jenkins. This is the scanner from the global configuration
        steps{
        withSonarQubeEnv('Sonarqube') { 
        // If you have configured more than one global server connection, you can specify its name
//      sh "${scannerHome}/bin/sonar-scanner"
        sh "mvn sonar:sonar"
        }
      }
     }
       
    }
}