#!groovy

node ('master') {
    checkout([
         $class: 'GitSCM',
         branches: [[name: '*/master']], 
         doGenerateSubmoduleConfigurations: false, 
     	 extensions: [], 
    	 submoduleCfg: [], 
    	 userRemoteConfigs: [[]]
    ])
}
