pipeline {
  agent any
  stages {
    stage('Parallel execution') {
      parallel {
        stage('Say Hello') {
          steps {
            sh 'echo "hello world"'
          }
        }

        stage('build app') {
          agent {
            docker {
              image 'gradle:jdk11'
              args 'ci/build-app.sh'
            }

          }
          steps {
            sh 'ci /build-app.sh'
          }
        }

      }
    }

  }
}