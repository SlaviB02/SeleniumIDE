pipeline {
    agent any

    evnviroment{
        CHROME_VERSION = '127.0.6533.73'
        CHROMEDRIVER_VERSION = '127.0.6533.72'
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