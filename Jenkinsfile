pipeline {
    agent any
    stages {
        stage('Checkout Code') {
            steps {
                checkout([$class: 'GitSCM', branches: [[name: '*/main']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[url: 'https://github.com/benyin12/ansible-flaskapp.git]]])
            }
        }
        stage('Deploy') {
            steps {
                sh '''
                ansible-playbook 2flaskplaybook.yaml -i hosts.ini
                '''
            }
        }
    }
}
