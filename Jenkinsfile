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
     stage('Git checkout') {
            steps {
                checkout([$class: 'GitSCM', branches: [[name: '*/anup']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[credentialsId: 'd3fb9088-8c56-4d86-a050-464cc85b990f', url: 'https://github.com/anupyadav1993/KSS-Jenkins.git']]])
            }
     stage('Run test') {
            steps {
                withEnv(["PATH+MAVEN=${tool 'maven4'}/bin"]) {
                sh "mvn test"
                }
            }
        }
    stage('Build war') {
            steps {
                withEnv(["PATH+MAVEN=${tool 'maven4'}/bin"]) {
                sh "mvn package"
                }
            }
        }
    }
}
