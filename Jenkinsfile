pipeline{
    agent any
    options{
        ansiColor('xterm')
        timestamps()
    }
    stages{
        stage("Code checkout"){
            steps{
                git branch: 'mavenWrapper', url: 'https://github.com/tomaszmariasik/junit4.git'
            }
        }
        stage("Build"){
            steps{
                sh './mvnw clean package'
            }
        }
        stage("Publish tests results"){
            steps{
                junit '**/target/surefire-reports/*.xml'
            }
        }
    }
}
