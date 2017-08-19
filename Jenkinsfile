pipeline {
    agent any
    tools {
        maven 'apache-maven-3.0.1' 
    }
    stages {
        stage('User Confirmation') {
            steps {
                input(message: 'Do you want to proceed, y or n', ok: 'y', 
                        parameters: [booleanParam(defaultValue: false, 
                        description: 'If you want to proceed, just push the button',name: 'Y?')])
            }
        }
    }}

