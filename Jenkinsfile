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
                bat 'mvn clean'
            }
        }
    stage('Scan Code') {
      steps {
        withSonarQubeEnv(installationName: 'Sonarqube') {
          sh './mvnw clean org.sonarsource.scanner.maven:sonar-maven-plugin:3.9.0.2155:sonar'
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