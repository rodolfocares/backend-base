pipeline {

    agent any
    stages{
        stage('etapa de construccion de aplicacion'){
            agent {
                docker{
                    image 'node:alpile3.20'
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