pipeline {
  agent {
    docker {
      image 'maven:3-alpine'
      args '-v /root/.m2:/root/.m2 --network=host'
    }

  }
  stages {
    stage('Build') {
      steps {
        sh 'mvn -B -DskipTests clean package'
      }
    }
    stage('Test 1') {
      parallel {
        stage('Test 1') {
          steps {
            sh 'echo "Everybody says Hi"'
          }
        }
        stage('Parallel Test 1') {
          steps {
            sh 'echo "Parallel test 1"'
          }
        }
      }
    }
  }
}