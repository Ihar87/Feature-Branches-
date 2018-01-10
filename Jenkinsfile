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

        sh("git config user.email ${repositoryCommiterEmail}")
        sh("git config user.name '${repositoryCommiterUsername}'")

        sh "git remote set-url origin git@github.com:..."

        // deletes current snapshot tag
        sh "git tag -d snapshot || true"
        // tags current changeset
        sh "git tag -a snapshot -m \"passed CI\""
        // deletes tag on remote in order not to fail pushing the new one
        sh "git push origin :refs/tags/snapshot"
        // pushes the tags
        sh "git push --tags"
        }
    }
}
