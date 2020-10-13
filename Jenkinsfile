pipeline {
  agent any

  tools {nodejs "NodeJs-12.3.1"}

  stages {
    stage('Checkout SCM') {
        git branch: 'master', url: 'https://github.com/stekontar/test.git'
    }

    stage('Install node modules') {
        sh "npm install"
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
