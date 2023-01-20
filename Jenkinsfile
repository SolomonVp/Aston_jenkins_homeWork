pipeline {
  agent any
  stages {
    stage('Log Tool Versions') {
      parallel {
        stage('Log Tool Versions') {
          steps {
            sh '''mvn --version

git --version java -version'''
          }
        }

        stage('Check for pom') {
          steps {
            fileExists 'pom.xml'
          }
        }

      }
    }

    stage('Build with maven') {
      steps {
        sh 'mvn compile test package'
      }
    }

    stage('Post Build Steps') {
      steps {
        writeFile(file: 'status.txt', text: 'Hey! It worked!')
      }
    }

  }
}