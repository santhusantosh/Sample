pipeline {
    agent any
    stages {
        stage("clone code"){
            steps{
              checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[url: 'https://github.com/santhusantosh/Sample.git']]])
            }
        }
        stage("build code")
            steps{
                build 'sample'
              sh "mvn clean install"
            }
        }
        stage("deploy"){
            steps{
              sshagent(['deploy_user']) {
                 echo "Deploying Sucessfully"
                 
                }
            }
        }
    }
}
