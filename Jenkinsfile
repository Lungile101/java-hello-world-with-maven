pipeline {
        agent any
    tools {
        maven "Apache Maven 3.9.8"
        }
    stages {
        stage('build') {
            steps {
                sh "mvn clean deploy -Dnew.version=${params.VERSION} -Dmule.environment=dev "
	            sh "mvn clean deploy -Dnew.version=${params.VERSION} -DmuleDeploy -Dmule.environment=dev -Ddeployment.environment=rtf-dev -X"
				}
            }
        }
    }
