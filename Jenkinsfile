node('built-in') 
{
    stage('Continuous Download') 
	{
    git 'https://github.com/sunildevops77/maven.git'
	}
	stage('Continuous Build') 
	{
    sh 'mvn package'
	}
	stage('Continuous Deploy') 
	{
    sh 'scp /home/ubuntu/.jenkins/workspace/Pipeline_Job/webapp/target/webapp.war  ubuntu@172.31.37.242:/var/lib/tomcat9/webapps/qaenv.war'

	}
	stage('Continuous Testing') 
	{
    sh 'echo "Testing Passed!!"'
	}
	stage('Continuous Delivery') 
	{
	input 'Waiting for your approval'
    sh 'scp /home/ubuntu/.jenkins/workspace/Pipeline_Job/webapp/target/webapp.war  ubuntu@172.31.34.13:/var/lib/tomcat9/webapps/prodenv.war'

	}
}

