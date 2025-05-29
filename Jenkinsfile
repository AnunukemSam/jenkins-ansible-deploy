pipeline {
    agent any

    environment {
        INVENTORY = 'inventory.ini'
        PLAYBOOK = 'deploy.yml'
    }

    stages {
        stage('Run Ansible Playbook') {
            steps {
                sh 'ansible-playbook -i $INVENTORY $PLAYBOOK'
            }
        }
    }
}
