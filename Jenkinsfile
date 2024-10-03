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
            stages{
                stage("test"){
                    steps{
                        sh 'npm run test'
                    }
                }
            }
            stages{
                stage("build"){
                    steps{
                        sh 'npm run build'
                    }
                }
            }

        }
        stage('construccion imagen docker'){
            steps{
                script{
                    sh 'docker build -t backend-base .'
                    sh 'docker tag backend-base us-central1-docker.pkg.dev/expertis-classroom/docker-repository/backend-base:rcm'
                }
            }
        }

    }

}