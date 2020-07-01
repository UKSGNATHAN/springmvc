@Library('sharedlibs-first') _
pipeline{
    agent any
    tools {
        maven 'maven3'
    }
    stages{
        stage('Maven Build'){
            steps{
                sh 'mvn clean package'
            }
        }
        stage ('tomcat deploy'){
            steps{
                tomcatdeploy credId: 'tomcatserver',
                             ip: '172.31.40.104',
                             userName: 'ec2-user',
                             tomcatHome: '/opt/tomcat8',
                             warName: 'springmvc'
            }
        }
    }
}
