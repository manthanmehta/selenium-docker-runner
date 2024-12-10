pipeline{

    agent any

    stages{

        stage('Start the Grid'){
            steps{
                sh "docker compose -f grid.yaml up -d"
            }
        }

        stage('Run the Tests'){
            steps{
                sh "docker compose -f test-suits.yaml up"
            }
        }
    }
    post {
        always{
        sh "docker compose -f grid.yaml up -d"
        }
    }
}