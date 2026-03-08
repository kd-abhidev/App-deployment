pipeline {
    agent any

    stages {
        stage('cleanws') {
            steps {
                cleanWs()
            }
        }
        stage(github) {
            steps {
                git 'https://github.com/kd-abhidev/App-deployment.git'
            }
        }
        stage(maven) {
            steps {
               sh '/opt/maven/bin/mvn clean package'
            }
        }
        
        stage(nexus) {
            steps {
                nexusArtifactUploader artifacts: [[artifactId: 'mywebapp', classifier: '', file: 'target/mywebapp-8.6.9.war', type: 'war']], credentialsId: '6c6ddeb1-31ac-4fc3-9301-be013b6cb34b', groupId: 'in.javahome', nexusUrl: 'http://65.2.149.71', nexusVersion: 'nexus3', protocol: 'http', repository: 'Deployment using Pipeline', version: '8.6.9'
            }
        }
        stage(tomcat) {
            steps {
                deploy adapters: [tomcat9(alternativeDeploymentContext: '', credentialsId: 'cred-of-tomcat', path: '', url: 'http://65.2.149.71')], contextPath: 'Pipeline-project', war: 'target/*.war'
            }
        }
    }
}

