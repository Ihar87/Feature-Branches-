#!groovy

stage 'Dev'
node ('master') {
    sh "pwd"
}
stage name: 'Staging', concurrency: 1
node ('Endeca') {
    sh "set"
}

