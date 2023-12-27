pipeline {
    agent any

    environment {
        AWS_REGION            = 'us-east-1'
        ELASTIC_BEANSTALK_APP = 'practice'
        ELASTIC_BEANSTALK_ENV =  'Practice-env'
    }

    stages {
        stage('Checkout') {
            steps {
                // You may need to configure your repository here
                checkout scm
            }
        }

        stage('Deploy to Elastic Beanstalk') {
            steps {
                script {
                    def elasticBeanstalk = [
                        region: "${AWS_REGION}",
                        applicationName: "${ELASTIC_BEANSTALK_APP}",
                        environmentName: "${ELASTIC_BEANSTALK_ENV}",
                        s3Bucket: 'yashbucketdhhffh',
                        // Other configuration options as needed
                    ]

                    elasticBeanstalkDeploy(deployment: elasticBeanstalk)
                }
            }
        }
    }
}
