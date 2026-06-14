pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                echo 'Pulling code from GitHub...'
                checkout scm
            }
        }

        stage('Validate Playbook') {
            steps {
                echo 'Validating Ansible playbook syntax...'
                sh 'ansible-playbook --syntax-check -i inventory/hosts.ini playbooks/harden.yml'
            }
        }

        stage('Run Ansible Playbook') {
            steps {
                echo 'Running hardening playbook...'
                sh 'ansible-playbook -i inventory/hosts.ini playbooks/harden.yml'
            }
        }
    }

    post {
        success {
            echo 'Server hardening completed successfully!'
        }
        failure {
            echo 'Hardening failed — check logs above.'
        }
    }
}