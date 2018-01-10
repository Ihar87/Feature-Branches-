#!groovy

node ('master') {
    stage ('checkout scm') {
        checkout scm
    }
    stage ('prepare platform') {
        load "${WORKSPACE}/ci-variables.groovy"
        sh '''
              set
              echo "${WORKSPACE}"
           '''
    }
}
