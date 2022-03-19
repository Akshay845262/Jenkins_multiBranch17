node('built-in') 
{
    stage('Continuous Download_master') 
	{
    git 'https://github.com/sunildevops77/maven.git'
	}
	stage('Continuous Build_master') 
	{
    sh 'mvn package'
	}
	stage('Continuous Deploy_master') 
	{
    sh 'scp /home/ubuntu/.jenkins/workspace/Pipeline_Job/webapp/target/webapp.war  ubuntu@172.31.37.242:/var/lib/tomcat9/webapps/qaenv.war'

	}
	stage('Continuous Testing_master') 
	{
    sh 'echo "Testing Passed!!"'
	}
	stage('Continuous Delivery_master') 
	{
	input 'Waiting for your approval'
    sh 'scp /home/ubuntu/.jenkins/workspace/Pipeline_Job/webapp/target/webapp.war  ubuntu@172.31.34.13:/var/lib/tomcat9/webapps/prodenv.war'

	}
}

