pipeline {
    agent any
    options {
        buildDiscarder logRotator(artifactDaysToKeepStr: '', artifactNumToKeepStr: '5', daysToKeepStr: '', numToKeepStr: '5')
    }
    stages {
        stage('Hello') {
            steps {
                sh '''
                    java -version
                '''
                sh """echo "Running newman tests with version"
                newman -v

                export DP_SERVICE_BASEURL="https://dev.client.canoo.com/v1"
                export AUTH_CLIENT_ID="maTDM26CJDil6suKzaFdPZSn8ki1X0qp"
                export AUTH_CLIENT_SECRET="rDkhaa3KRZ64T4UIe5A_ZIq-S9qT4mFWhvzG8KReaBzQzpE_ZSwqCTocPW1Qmdyo"
                export API_DRIVER_NAME="pashaemail@yahoo.com"
                export API_DRIVER_PASS="@Test123456!"

                newman run postman/scripts/canoo-js-service-client-pke.postman_collection.json \
                --env-var "baseUrl=${DP_SERVICE_BASEURL}" \
                --env-var "client_id=${AUTH_CLIENT_ID}" \
                --env-var "client_secret=${AUTH_CLIENT_SECRET}" \
                --env-var "username=${API_DRIVER_NAME}" \
                --env-var "userpass=${API_DRIVER_PASS}"
                """



            }
        }
    }
}
