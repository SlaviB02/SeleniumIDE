pipeline {
    agent any

    environment{
        CHROME_VERSION = '137.0.7151.70'
        CHROMEDRIVER_VERSION = '137.0.7151.70'
        CHROME_INSTALL_PATH = 'C:\\Program Files\\Google\\Chrome\\Application'
        CHROMEDRIVER_PATH = '"C:\\Program Files\\Google\\Chrome\\Application\\chromedriver.exe"'
    }

    tools { 
        msbuild 'MSBuild-v6'
    }

    stages {
        stage('Checkout Code') {
            steps {
                checkout scm
            }
        }
        
        stage('Build app') {
            steps {
                 bat 'dotnet build'
            }
        }


        stage('Run Tests') {
            steps {
                 bat 'dotnet test'
            }
        }
    }
}
