pipeline {
    agent any

    environment {
        VENV = 'venv'
        PYTHON = 'python'
    }

    stages {
        stage("Install Git and Python") {
            steps {
                bat '''
                    choco install -y git
                    choco install -y python
                    refreshenv
                '''
            }
        }

        stage("Setup Python Environment") {
            steps {
                bat '''
                    python --version
                    python -m venv %VENV%
                    call %VENV%\\Scripts\\activate
                    %VENV%\\Scripts\\pip.exe install --upgrade pip
                    %VENV%\\Scripts\\pip.exe install -r requirements.txt
                '''
            }
        }

        stage("Linting") {
            steps {
                echo "Linting the code..."
            }
        }

        stage("Install Packages") {
            steps {
                echo "Installing additional packages..."
            }
        }

        stage("Build Docker Image") {
            steps {
                bat 'docker build -t myapp:latest .'
            }
        }

        stage("Run Application") {
            steps {
                echo "Running the application..."
            }
        }
    }
}

