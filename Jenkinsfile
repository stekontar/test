

pipeline {
  agent any

  tools {nodejs "NodeJs-12.3.1"}

  stages {
    stage('Checkout SCM') {
        steps {
            git branch: 'master', url: 'https://github.com/stekontar/test.git'
        }
    }

    stage('Install node modules') {
        steps {
            sh "npm install"
        }
    }

    stage("Test") {
        steps {
            sh "npm run test-headless"
        }
    }

    stage("Build") {
        steps {
            sh "npm run build --prod"
        }
    }
  }
}
