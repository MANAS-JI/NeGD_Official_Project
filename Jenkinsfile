pipeline {
    agent any

    stages {

        stage('Checkout Code') {
            steps {
                echo "Pulling latest code from GitHub..."
                checkout scm
            }
        }

        stage('Copy to XAMPP htdocs') {
            steps {
                echo "Copying project files to XAMPP2 htdocs..."
                bat '''
                    xcopy * "C:\\XAMPP2\\htdocs\\InternetBanking-PHP" /E /H /C /Y
                '''
            }
        }

        stage('Restart Apache Server') {
            steps {
                echo "Restarting Apache..."
                bat '''
                    C:\\XAMPP2\\xampp_stop.exe
                    C:\\XAMPP2\\xampp_start.exe
                '''
            }
        }
    }
}
