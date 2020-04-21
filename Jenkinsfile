def mvnHome ;
def JAVA_HOME;
​
node() {
    stage('Preparation') {
       JAVA_HOME = tool 'jdk8'
       mvnHome = tool 'm3'
    }
    stage('Checkout SCM') {
        git branch: 'master', url: 'https://github.com/atinsingh/spring-prj1.git'
    }
    stage('Slack Notification') {
        slackSend baseUrl: 'https://hooks.slack.com/services/', channel: '#devops_march', color: 'good', message: "Build Started: ${env.JOB_NAME} ${env.BUILD_NUMBER}", teamDomain: 'pragraconsulting2020', tokenCredentialId: 'slack'
    }
    stage('Compile') {
        sh "'${mvnHome}/bin/mvn' compile" 
    }
    stage('Test') {
        sh " '${mvnHome}/bin/mvn' test" 
    }
   stage('Package') {
        sh "'${mvnHome}/bin/mvn' package" 
   }  
}
