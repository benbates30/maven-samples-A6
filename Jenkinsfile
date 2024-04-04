pipeline {
  agent any
  tools {
      maven 'maven_auto'
      jdk 'java11'
  }
  stages {
    stage('checkout') {
      steps {
        git(url: 'https://github.com/benbates30/maven-samples-A6', branch: 'master')
      }
    }
    stage('run') {
      agent any
      steps {
        sh '''git bisect start 198644632661c67b6c32f59e9047c11a70685e15  98ac319c0cff47b4d39a1a7b61b4e195cfa231e5
'''
        sh 'git bisect run mvn clean test'
      }
    }
  }
}