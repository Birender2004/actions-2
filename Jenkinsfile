pipeline{
    agent any

    stages{
        stage("Build"){
            steps{
                echo "Building docker image"
                sh 'docker build -t yes-login .'
            }
        }

        stage("Run"){
            steps{
                sh 'rm -f yes-log || true'
                sh 'docker run -d -p 5000:5000 --name yes-log yes-login'
            }
        }
    }
}