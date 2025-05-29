pipeline {
    agent any

    environment {
        INVENTORY = 'ansible/inventory.ini'
        PLAYBOOK = 'ansible/deploy.yml'
    }

    stages {
        stage('Run Ansible Playbook') {
            steps {
                sh 'ansible-playbook -i $INVENTORY $PLAYBOOK'
            }
        }
    }
}
