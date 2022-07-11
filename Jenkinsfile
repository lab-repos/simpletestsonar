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
       
  stage('SonarQube Analysis') {
    def scannerHome = tool 'SonarScanner';
    withSonarQubeEnv() {
      sh "${scannerHome}/bin/sonar-scanner"
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