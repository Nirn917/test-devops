pipeline {
  agent {
    docker {
      args '-u root:root -p 3000:80'
      image 'ubuntu:xenial'
    }

  }
  stages {
    stage('Build') {
      steps {
        sh '''apt update
apt install -y apache2 nodejs npm curl
/etc/init.d/apache2 start
cp ./index.html /var/www/html/
npm i html-validator-cli -g
ln -s /usr/bin/nodejs /usr/bin/node
html-validator --file=./index.html

'''
      }
    }

    stage('Test') {
      steps {
        sh '''pwd
cd /var/www/html
pwd
cat index.html'''
      }
    }

  }
}