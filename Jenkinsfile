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
    stage('Clean Code') {
            steps {
                echo 'Cleaning...'
            }
        }
    stage('Scan Code') {
      steps {
        withSonarQubeEnv(installationName:'Sonarqube') {
          sh '${scannerHome}/bin/sonar-scanner'
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