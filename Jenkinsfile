pipeline {
  agent {
    docker {
      image 'node:14'
    }
  }
  stages {
    stage('Clone repository') {
      steps {
        git branch: 'main',
          url: 'https://github.com/vanillacoke77/pes1ug22am922_Jenkins.git'
      }
    }
    stage('Install dependencies') {
      steps {
        sh 'npm install'
      }
    }
    stage('Build application') {
      steps {
        sh 'npm run build'
      }
    }
    stage('Test application') {
      steps {
        sh 'npm test'
      }
    }
    stage('Push Docker image') {
      steps {
        sh 'docker build -t vanillacoke77/pes1ug22am922:$BUILD_NUMBER ."
        sh 'docker push -t vanillacoke77/pes1ug22am922:$BUILD_NUMBER ."
      }
    }
  }
}
