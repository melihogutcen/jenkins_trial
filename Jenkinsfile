// CODE_CHANGES == getGitChanges()
pipeline {
    agent any
    /*environment{
        NEW_VERSION = '1.3.0'
        SERVER_CREDENTIALS = credentials('server-credentials')
    } */
    /* tools {
        maven 'Maven'
    }*/
    parameters{
        //string(name: 'VERSION',defaultValue:'',description:'version to deploy on prod')
        choice(name: 'VERSION',choices:['1.1.0','1.2.0','1.3.0'],description:'')
        booleanParam(name: 'executeTests',defaultValue: true, description:'')
        }
    stages {
        stage('Build') {
           /* when {
                expression {
                    BRANCH_NAME == 'dev' && CODE_CHANGES == true 
                }
            } */
            steps {
                echo 'Building....'
                // echo "Building version ${NEW_VERSION}"
            }
        }
        stage('Test') {
            when {
                expression {
                    // BRANCH_NAME == 'dev' || BRANCH_NAME == 'master' 
                    params.executeTests
                }
            } 
            steps {
                echo 'Testing.....'
            }
        }
        stage('Deployment') {
            steps {
                echo 'Deploying.....'
                echo "Deploying ${params.VERSION}"
                /* echo "Deploying with ${SERVER_CREDENTIALS}"
                sh "${SERVER_CREDENTIALS}"
                withCredentials([
                    usernamePassword(credentials: 'server-credentials',usernameVariable:USER,passwordVariable: PWD)
                    ]){
                        sh "heyy ${USER} ${PWD}"
                    }
                */
            }
        }
    }
}
    /* post {
        always{
            //
            }
        success{
            
        }
        failure{
            
        }
    } */


