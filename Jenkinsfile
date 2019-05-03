node('linux'){
    stage('Test'){
        git 'https://github.com/Vsackor/java-project.git'
        sh 'ant -buildfile test.xml'
        sh 'ant -f test.xml -v'
    }
    
    stage('Build'){
        sh 'ant -f build.xml -v'
    }
    
    stage('Reports'){
        junit 'reports/*.xml '
    }
}
