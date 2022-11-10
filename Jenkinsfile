pipeline {
    agent any 
    triggers { 
        cron('* * * * *')
    }
    
  
    stages {
        stage('production stage') {
            steps {
                sh 'systemctl status apache2'
            }
        }
        stage('test stage') {
            steps {
                sh 'systemctl status tomcat9'
            }
        }
   
        stage('production') {
            when {
                branch 'main'
            }
            steps {
                sh 'cp index.html /var/www/html'
            }
        }
        stage('Testing-branch') {
            when {
                branch 'branch1'
            }
            steps {
                sh 'cp index.html /var/lib/tomcat9/webapps/abcd'
            }
        }
    }
}
