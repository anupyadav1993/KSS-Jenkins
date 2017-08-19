pipeline {
    agent any
    stages {
        stage('User Confirmation') {
            steps {
                input(message: 'Do you want to proceed, y or n', ok: 'y', 
                        parameters: [booleanParam(defaultValue: false, 
                        description: 'If you want to proceed, just push the button',name: 'Y?')])
            }
        }
        stage('Git Checkout') {
            steps {
                checkout([$class: 'GitSCM', branches: [[name: '*/anup']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[credentialsId: 'c8541ba1-0143-4fcd-b447-89034f5147ef', url: 'git@github.com:anupyadav1993/KSS-Jenkins.git']]])
            }
        }
    }
}

