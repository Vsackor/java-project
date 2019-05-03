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
		 git credentialsId: '6eb0bee4-aa59-4b6e-b8a7-d2781f3777e8', url: 'https://github.com/Vsackor/java-project.git' > arn:aws:s3:::cf-templates-khqlru1bms20-us-east-1        
		 sh 'cat README.md'  
    }    
    stage('Reports'){
        junit 'reports/*.xml '
    }
}
