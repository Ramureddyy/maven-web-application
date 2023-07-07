node
{
def mavenHome = tool name: "maven3.9.2"
properties([buildDiscarder(logRotator(artifactDaysToKeepStr: '', artifactNumToKeepStr: '5', daysToKeepStr: '', numToKeepStr: '5')), [$class: 'JobLocalConfiguration', changeReasonComment: ''], pipelineTriggers([pollSCM('* * * * *')])])
stage('CheckoutCode')
{	
git credentialsId: '7792293a-9d28-41d4-b00b-49854ed1f876', url: 'https://github.com/Ramureddyy/maven-web-application.git'
}
stage('Build')
{
sh "${mavenHome}/bin/mvn clean package"
}
/*
stage('ExicuteSonarQubeReport')
{
sh "${mavenHome}/bin/mvn sonar:sonar"
}
stage('UploadArtifactsintoNexus')
{
sh "${mavenHome}/bin/mvn deploy"
}
stage('deployintointoTomcatServer')
{
sshagent(['50f183de-cd8a-418f-a67d-7af5db096813']) {
sh "scp -o StrictHostKeyChecking=no target/maven-web-application.war ec2-user@18.207.151.248:/opt/apache-tomcat-10.1.9/webapps/"
} 
}
*/
}
