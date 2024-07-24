pipeline {
        agent any
    tools {
        maven 'apache-maven-3.9.8'
        }
    stages {
        stage('Prepare') {
                steps {
                        configFileProvider([configFile(fileId: "59cb371e-a339-4ce6-9b80-39e3771efe08" , targetLocation: 'env.groovy', variable: 'ENV')]) {
                            load "env.groovy";
                        }
                }
        }
        stage('development-branch') {
            when {
                branch 'master'
            }
            steps {
                sh "mvn clean deploy -Dnew.version=${params.VERSION} -Dmule.environment=dev "
	            sh "mvn clean deploy -Dnew.version=${params.VERSION} -DmuleDeploy -Dmule.environment=dev -Ddeployment.environment=rtf-dev -X"
				}
            }
        }
    }
