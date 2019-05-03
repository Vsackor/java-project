node('linux'){
		    stage('Test'){
		        git 'https://github.com/Vsackor/java-project.git'
		        sh 'ant -buildfile test.xml'
		        sh 'ant -f test.xml -v'
		    }
		    
		    stage('Build'){
		        sh 'ant -f build.xml -v'
		    }
		    
		    stage('Deploy'){
		         git credentialsId: '6eb0bee4-aa59-4b6e-b8a7-d2781f3777e8', url: 'https://github.com/Vsackor/java-project.git' 'aws s3 cp s3:// cf-templates-khqlru1bms20-us-1'
		         sh 'cat README.md'  
		    }
		    
		    stage('Reports'){
		        withCredentials([[$class: 'AmazonWebServicesCredentialsBinding', accessKeyVariable: 'AWS_ACCESS_KEY_ID', credentialsId: '6241646a-1dc7-4e90-b959-484c477cbde9', secretKeyVariable: 'AWS_SECRET_ACCESS_KEY']]) {
		          sh 'aws cloudformation describe-stack-resources --region us-east-1 --stack-name Jenkins'
		          junit 'reports/*.xml '
               }
		       
		    }
		
}
