pipeline {

    agent any
    environment{
        NPM_CONFIG_CACHE = "{WORKSPACE}/.npm"
    }
    stages{
        stage('etapa de construccion de aplicacion'){
            agent {
                docker{
                    image 'node:alpine3.20'
                    reuseNode true
                }
            }
            stages{
                stage("isntall"){
                    steps{
                        sh 'npm install'
                    }
                }
            }

        }
    }

}