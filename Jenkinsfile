pipeline {
  agent any

  stages {
    stage('Checkout') {
        steps {
          // Get some code from a GitHub repository
          git branch: 'main', url: 'https://github.com/mominam89/lbg-vat-calculator.git'
        }
    }
    stage('SonarQube Analysis') {
      environment {
        scannerHome = tool 'sonar'
      }
        steps {
            withSonarQubeEnv('sonar-qube-1') {        
              sh "${scannerHome}/bin/sonar-scanner"
            }   
        }
    }
  }
}
