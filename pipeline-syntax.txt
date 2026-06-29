pipeline {
    agent any
    tools {
        maven "mymaven"
    }
    stages {
        stage('Code') {
            steps {
                git "https://github.com/nehapyla/one.git"
            }
        }
        stage ('CQA') {
            steps {
                withSonarQubeEnv('mysonar') {
                    sh '''
                    mvn sonar:sonar \
                        -Dsonar.projectKey=MyProject \
                        -Dsonar.host.url=http://16.16.208.198:9000 \
                        -Dsonar.login=b1e32a2549e166b50d5ea6400fe32e0852363f26
                    '''
                }
            }
        }
        stage ('Build&Test') {
            steps {
                sh 'mvn clean package'
            }
        }
        stage ('Artifact') {
            steps {
                nexusArtifactUploader artifacts: [[artifactId: 'myweb', classifier: '', file: 'target/myweb-8.7.3.war', type: 'war']], credentialsId: 'sonar', groupId: 'in.javahome', nexusUrl: '16.16.110.253:8081', nexusVersion: 'nexus3', protocol: 'http', repository: 'myrepo', version: '8.7.3'
            }
        }
        stage ('Deploy') {
            input {
                message "Can I Deploy?"
            }
            steps {
                deploy adapters: [tomcat9(alternativeDeploymentContext: '', credentialsId: 'tomcat', path: '', url: 'http://13.48.128.210:8080/')], contextPath: 'website', war: 'target/*.war'
            }
        }
    }
    post {
        always {
            mail to: 'pylaneha26@gmail.com',
            subject: "PIPELINE STATUS: ${env.JOB_NAME} #${env.BUILD_NUMBER}",
            body: "*${currentBuild.currentResult}:* Job ${env.JOB_NAME} \n build ${env.BUILD_NUMBER} \n More info at: ${env.BUILD_URL}"
        }
    }
}

