node('skynetinstance') 
{
     def mavenHome=tool name: "maven3.8.3"                                                                                                 
    stage('CheckOUtCodefromGit')
    {
        git branch: 'development', credentialsId: '47700b5d-52c8-4438-8c9f-58c55ab8a632', url: 'https://github.com/palakuru/maven-web-application.git'
    }
	
	stage('BildPackagesuingMaven')
	{
	 sh "${mavenHome}/bin/mvn clean package"
	}
	/*
	stage('sonarqubereport')
	{
	sh "${mavenHome}/bin/mvn clean sonar:sonar"
	}
	
    stage('storeartifactsinrepository')
	{
	sh "${mavenHome}/bin/mvn clean deploy"
	}
	
	stage('deployapplicationintotomcat')
	{
	sshagent(['c5983431-61bb-473c-9087-a96ed0208960']) {
    sh "scp -o StrictHostKeyChecking=no target/maven-web-application.war ec2-user@3.110.44.206 /opt/apache-tomcat-9.0.54/webapps/"
	sh "scp -o StrictHostKeyChecking=no target/maven-web-application.war ec2-user@13.235.132.183:/opt/apache-tomcat-9.0.29/webapps/"
    }
	}
	*/
	stage('buildstatusthroughmail')
	{
	emailext body: '''buildis over
    regards,
    naveen''', subject: 'builover', to: 'npalakuru'
	}
}
