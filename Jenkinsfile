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
    stage ('add tag') {
        if (env.BRANCH_NAME == 'master') {
            println ("tagging")
            sshagent (credentials: ['f447e8a7-4522-4bcd-aadc-398cb2b0cc10'])
            sh "git tag -d ci-${JOB_BASE_NAME}-${BUILD_NUMBER} || true"
            sh "git push origin :refs/tags/ci-${JOB_BASE_NAME}-${BUILD_NUMBER} || true"
            sh "git tag -a ci-${JOB_BASE_NAME}-${BUILD_NUMBER} -m 'CI Tag'"
            sh "git push origin refs/tags/ci-${JOB_BASE_NAME}-${BUILD_NUMBER}"
        }
    }
}
