node{
	def mavenhome = tool name: "Maven 3.9.6"
	
	stage('checkoutcode')
	{
	git branch: 'development', credentialsId: 'c60a7cd6-102f-4fbc-91f6-22cdec0aba4b', url: 'https://github.com/ddineshgopi/maven-web-app.git'
	}
	
	stage('Build')
	{
	sh "${mavenhome}/bin/mvn clean package"
	}
/*	
	stage('Report Generation')
	{
	sh "${mavenhome}/bin/mvn clean sonar:sonar"
	}
	
	stage('Upload Artifacts into Remote Repo')
	{
	sh "${mavenhome}/bin/mvn clean deploy"
	}
	
	stage('Deploy the App into Tomcat Server')
	{
	sshagent(['b3accaa5-727f-4bd5-8cce-53dd416569b6']) {
    	sh "scp -o StrictHostKeyChecking=no target/maven-web-application.war ec2-user@3.84.6.31:/opt/apache-tomcat-9.0.83/webapps/"
	}
	}
*/	
	stage('Send Email Notification')
	{
	emailext body: '''Build Over..!

Regards,
Dinesh,
7904632708''', subject: 'Build Over..!', to: 'dinesh991995@gmail.com'
	}
	
    }	
     
   
