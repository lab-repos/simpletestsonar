pipeline {
    triggers {
    githubPush()
    }

    agent {
        any {
            image 'node:latest'
            args '-u root'
        }
    }
       
  stages {
    stage('Scan') {
            steps('SonarQube Analysis') {
                // def scannerHome = tool 'Sonar-Scanner';
                withSonarQubeEnv(installationName:'Sonarqube') {
                bat "${scannerHome}/bin/sonar-scanner"
                }
            }
    }
    stage('Compile') {
            steps {
                echo 'Compiling...'
                // bat 'npm install'
            }
        }
    stage('Analyse') {
            steps {
                echo 'Analysing...'
            
            }
        }

    
    stage('Build') {
            steps {
                echo 'Building...'
                // bat 'npm run build'
            }
        }
    stage('Test') {
            steps {
                echo 'Testing...'
                
            }
        }

  }
}