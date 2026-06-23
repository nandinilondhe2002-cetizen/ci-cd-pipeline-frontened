pipeline {
    agent any

    parameters {
        string(name: 'S3_BUCKET', defaultValue: 'ci-cd-project-nandini', description: 'S3 Bucket for frontend deployment')
    }

    environment {
        BUCKET = "${params.S3_BUCKET}"
    }

    stages {
        stage('Deploy to S3') {
            steps {
                sh """
               /usr/local/bin/aws s3 cp ./index.html s3://$BUCKET/
               /usr/local/bin/aws s3 cp ./frontend_version.json s3://$BUCKET/
                """
            }
        }
    }
}
