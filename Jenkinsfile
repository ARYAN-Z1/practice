pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/ARYAN-Z1/practice.git'
            }
        }

        stage('Validate Files') {
            steps {
                script {
                    echo "Checking if index.html and style.css exist..."
                    sh '''
                    if [ -f index.html ] && [ -f style.css ]; then
                      echo "✅ Files exist!"
                    else
                      echo "❌ Missing files!"
                      exit 1
                    fi
                    '''
                }
            }
        }

        stage('HTML Lint Check') {
            steps {
                sh '''
                echo "Performing basic HTML validation..."
                if grep -q "<html" index.html; then
                  echo "✅ HTML looks fine"
                else
                  echo "❌ Invalid HTML structure"
                  exit 1
                fi
                '''
            }
        }

        stage('Deploy / Build') {
            steps {
                echo "You can add deployment or copy commands here later."
            }
        }
    }

    post {
        success {
            echo "✅ Pipeline completed successfully!"
        }
        failure {
            echo "❌ Pipeline failed!"
        }
    }
}
