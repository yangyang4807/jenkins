pipeline {
    agent any
    stages {

   stage('git checkout') {
       checkout([$class: 'GitSCM', branches: [[name: '${branch}']], doGenerateSubmoduleConfigurations: false, extensions: [], subm
oduleCfg: [], userRemoteConfigs: [[url: 'https://github.com/yangyang4807/jenkins.git']]])
   }
   stage('code copy') {
        sh '''rm -rf ${WORKSPACE}/.git
        mv /webser/www1/phpnew /webser/wp.com-$(date +"%F_%T")
        cp -rf ${WORKSPACE} /webser/www1/phpnew'''
   }
   stage('test') {
       sh "curl http://192.168.88.122"
   }


    }

}
