pipeline {
  agent {
    docker {
      image 'httpd:2.4.41'
      args '-u root:root -p 3000:80'
    }

  }
  stages {
    stage('Build') {
      steps {
        sh '''cp ./index.html /usr/local/apache2/htdocs/
'''
      }
    }

    stage('test') {
      agent {
        docker {
          image 'node:latest'
          args '-p 3200:3000 -u root:root'
        }

      }
      steps {
        sh '''npm i html-validator-cli -g
html-validator --file=./index.html
'''
      }
    }

  }
}