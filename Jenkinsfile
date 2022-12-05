pipeline {
  agent { 
    label 'build-in'
  } 
  stages {
    stage('Status') {
	  steps {
	    sh 'liquibase status --url="jdbc:mysql://mysqldb3.c5kvdhfba2on.ap-south-1.rds.amazonaws.com:3306/myapp" --changeLogFile=my_app-wrapper.xml  --username=$DB_CREDS_USR --password=$DB_CREDS_PSW'
	  }
    }
    stage('Update') {
      steps {
        sh 'liquibase update --url="jdbc:mysql://mysqldb3.c5kvdhfba2on.ap-south-1.rds.amazonaws.com:3306/myapp" --changeLogFile=my_app-wrapper.xml --username=$DB_CREDS_USR --password=$DB_CREDS_PSW'
      }
    }
  }
}
