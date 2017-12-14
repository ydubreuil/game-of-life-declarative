#!groovy

pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        // Maven installation declared in the Jenkins "Global Tool Configuration"
        withMaven(maven: 'M3') {
          sh 'mvn -B clean verify'
        }
      }
    }
    stage('Acceptance tests') {
      steps {
        dir('gameoflife-acceptance-tests') {
          withMaven(maven: 'M3') {
            sh 'mvn -B clean verify'
          }
        }
      }
    }
  }
}

