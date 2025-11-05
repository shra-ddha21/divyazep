pipeline {
    agent any

    stages {
        stage('Checkout Code') {
            steps {
                echo 'Pulling code from GitHub...'
                checkout scm
            }
        }

        stage('Build & Test') {
            steps {
                echo 'Building the code and running tests...'
                // Add build/test commands here if needed
            }
        }

        stage('Deploy with Ansible') {
            steps {
                echo 'Deploying using Ansible playbook...'
                sh 'ansible-playbook /opt/ansible/deploy.yml'
            }
        }

        stage('Track Model with MLflow') {
            steps {
                echo 'Logging model metrics to MLflow...'
                sh '/home/ubuntu/mlops/venv/bin/python /home/ubuntu/track_with_mlflow.py'
            }
        }

        stage('Deploy to Kubernetes') {
            steps {
                echo 'Deploying application to Kubernetes (simulated)...'
                sh 'echo "Kubernetes deployment simulated"'
            }
        }
    }
}
