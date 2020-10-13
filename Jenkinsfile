pipeline {
    agent {
        docker {
            image 'node:12.11.0-alpine'
            args '-p 3000:3000'
        }
    }
    environment {
        CI = 'true'
    }
    stages {

      stage('Checkout SCM') {
          git branch: 'master', url: 'https://github.com/stekontar/test.git'
      }

      stage('Install node modules') {
          sh "npm install"
      }

      stage("Test") {
          sh "npm run test-headless"
      }

      stage("Build") {
          sh "npm run build --prod"
      }
    }
}
