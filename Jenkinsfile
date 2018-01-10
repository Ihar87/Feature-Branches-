#!groovy

node ('master') {
    stage ('checkout scm') {
        checkout scm
    }
    stage ('compilation checks') {
        println ("load env vars")
        load "${WORKSPACE}/ci-variables.groovy"
        println ("creating/removing symblink")
        println ("ant build")
    }
    stage ('quality gates') {
        println ("SQL verification")
        println ("XML verification")
        println ("JSP verification")
        println ("Unit tests")
        println ("Static code analysis for diff in commit")
    }
}
