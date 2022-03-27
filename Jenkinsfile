pipeline {
  agent {
    node {
      label 'demo-web'
    }

  }
  stages {
    stage('Build image') {
      steps {
        sh 'docker build -t docker-reactjs .'
      }
    }

    stage('Delete old container') {
      steps {
        sh 'docker rm -f docker-reactjs'
      }
    }

    stage('Run new container') {
      steps {
        sh 'docker run -p 50000:80 -d --name docker-reactjs docker-reactjs'
      }
    }

  }
}