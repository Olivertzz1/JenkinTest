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
                echo 'Skip dotnet test: classic VB Web Application uses MSBuild tests if any'
            }
        }
    }

    post {
        always {
            echo 'Build finished'
        }
    }
}
