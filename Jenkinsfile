#!groovy

stage 'Dev'
node ('master') {
    sh "sudo yum update -y"
}

stage name: 'Staging', concurrency: 1
node ('Endeca') {
    sh "set"
}

