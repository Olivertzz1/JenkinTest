pipeline {
    agent any

    stages {
        stage('Restore') {
            steps {
                bat 'nuget restore JenkinTest.sln'
            }
        }

        stage('Build') {
            steps {
                bat '"C:\\Program Files (x86)\\Microsoft Visual Studio\\2022\\BuildTools\\MSBuild\\Current\\Bin\\MSBuild.exe" JenkinTest\\JenkinTest.vbproj /p:Configuration=Release'
            }
        }

        stage('Test') {
            steps {
                bat 'dotnet test --no-build --configuration Release'
            }
        }
    }

    post {
        always {
            echo 'Build finished'
        }
    }
}
