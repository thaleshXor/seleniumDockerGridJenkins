pipeline {
  agent any
  stages {
    stage('checkout') {
      steps {
        git(url: 'https://github.com/thaleshXor/seleniumDockerGridJenkins', branch: 'master')
      }
    }

    stage('execution') {
      parallel {
        stage('chrome') {
          steps {
            sh 'mvn test -DvarTestng="testng1.xml"'
          }
        }

        stage('firefox') {
          steps {
            sh 'mvn test -DvarTestng="testng2.xml"'
          }
        }

      }
    }

  }
}