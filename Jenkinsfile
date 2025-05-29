pipeline {
    agent any

    environment {
        INVENTORY = 'ansible/inventory.ini'
        PLAYBOOK = 'ansible/deploy.yml'
    }

    stages {
        stage('Checkout Code') {
            steps {
                git 'https://github.com/yourusername/static-html-ci-cd.git'
            }
        }

        stage('Install Ansible') {
            steps {
                sh '''
                if ! command -v ansible &> /dev/null; then
                  sudo apt update && sudo apt install -y ansible
                fi
                '''
            }
        }

        stage('Run Ansible Playbook') {
            steps {
                sh 'ansible-playbook -i $INVENTORY $PLAYBOOK'
            }
        }
    }
}
