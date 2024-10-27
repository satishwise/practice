pipeline
{
	agent any
	stages
	{
		stage("cont_download")
		{
			steps
			{
			git branch: 'main', url: 'https://github.com/nocturnaldevops/Project1.git'
			}
		}
		stage("cont_build")
		{
			steps
			{
			sh 'mvn package'
			}
		}
	stage("cont_deploy_to_test")
	{
	steps{
	deploy adapters: [tomcat9(credentialsId: 'f15282f8-b1ae-4c48-9dba-8b6e1868d367', path: '', url: 'http://172.31.5.175:8080')], contextPath: 'testwar', war: '**/*.war'
	}
	}
	stage("cont_test")
	{
	steps{
	mail bcc: 'satishwise@gmail.com', body: '''Dear Team,
please test the application deployed on to test server on this url http://13.235.91.181:8080/test
''', cc: 'satish.dbadmin@gmail.com', from: '', replyTo: '', subject: 'First Scripted Pipeline', to: 'satishwise.devops@gmail.com'
	}
	}
	stage("cont_delivery")
	{
	steps{
	mail bcc: 'satishwise@gmail.com', body: '''Dear Team,
please test the application deployed on to test server on this url http://13.235.91.181:8080/test
''', cc: 'satish.dbadmin@gmail.com', from: '', replyTo: '', subject: 'First Scripted Pipeline', to: 'satishwise.devops@gmail.com'
	}
	}
    }
    }
