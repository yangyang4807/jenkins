pipeline {
    agent any
    stages {

   stage('git checkout') {
       checkout([$class: 'GitSCM', branches: [[name: '${branch}']], doGenerateSubmoduleConfigurations: false, extensions: [], subm
oduleCfg: [], userRemoteConfigs: [[url: 'git@172.16.1.3:/home/git/repos/wordpress']]])
   }
   stage('code copy') {
        sh '''rm -rf ${WORKSPACE}/.git
        mv /usr/share/nginx/html/wp.com /data/backup/wp.com-$(date +"%F_%T")
        cp -rf ${WORKSPACE} /usr/share/nginx/html/wp.com'''
   }
   stage('test') {
       sh "curl http://wp.test.com/status.html"
   }


    }

}
