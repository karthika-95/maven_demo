pipeline {
    agent any
    stages {
stage('scm') {
steps {
    git 'https://github.com/karthika-95/maven_demo'
    }
}
    stage('build') {
    steps {
        withMaven(maven : 'maven'){
        bat "mvn clean install"
    }
    }
}
    stage('junit') {
steps {
    junit healthScaleFactor: 10.0, testResults: '**/gameoflife-web/target/surefire-reports/*.xml'
    }
}
    stage('deploy') {
steps {
    bat 'copy "C:\\Program Files (x86)\\Jenkins\\workspace\\raghuproject\\gameoflife-web\\target\\*.war" "C:\\Program Files\\Apache Software Foundation\\Tomcat 9.0\\webapps\\"'
    }
}
}
}
