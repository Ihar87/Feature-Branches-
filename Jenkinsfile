#!groovy

stage 'Dev'
node ('master') {
    sh "who am i"
}
stage name: 'Staging', concurrency: 1
node ('Endeca') {
    sh "who am i"
}

