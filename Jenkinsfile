pipeline {
  agent {
    docker {
      image 'maven:3-alpine'
      args '-v /root/.m2:/root/.m2 --network=host'
    }

  }
  stages {
    stage('Build') {
      parallel {
        stage('Build') {
          steps {
            sh 'mvn -B -DskipTests clean package'
          }
        }
        stage('Build2') {
          steps {
            echo 'We are build too'
          }
        }
      }
    }
    stage('Test') {
      steps {
        echo 'Hello from test'
      }
    }
  }
}