pipeline {
    agent any

    environment {
        VENV = 'venv'
    }

    stages {
        stage ("Install") {
            steps {
                bat '''
                    python -m venv %VENV%
                    call %VENV%\\Scripts\\activate
                    pip install --upgrade pip
                    pip install -r requirements.txt
                '''
            }
        }

        stage ("Linting") {
            steps {
                echo "This is my Linting Step"
            }
        }

        stage ("Install Packages") {
            steps {
                echo "This is Install Packages Step"
            }
        }

        stage ("Run Application") {
            steps {
                echo "This is my Run application Step"
            }
        }
    }
}
