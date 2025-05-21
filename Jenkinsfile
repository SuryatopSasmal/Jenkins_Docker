pipeline {
    agent any

    environment {
        VENV = 'venv'
    }

    stages {
        stage("Install") {
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
                echo "This is my Linting Step"
            }
        }

        stage("Install Packages") {
            steps {
                echo "This is Install Packages Step"
            }
        }

        stage("Run Application") {
            steps {
                echo "This is my Run Application Step"
            }
        }
    }
}
