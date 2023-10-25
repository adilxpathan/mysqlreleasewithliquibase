pipeline {
  agent any
  environment {
    DB_CREDS=credentials('mysql-db-credentials')
  } 
  stages {
    stage('Status') {
	  steps {
	    sh 'sudo liquibase status --url="jdbc:mysql://demo.cly2fnimcg0u.ap-south-1.rds.amazonaws.com:3306/demo?useSSL=false" --changeLogFile=db.changelog.xml  --username=$DB_CREDS_USR --password=$DB_CREDS_PSW'
	  }
    }
   /* stage('Diff') {
	  steps {
	    sh 'sudo liquibase diff --url="jdbc:mysql://demo.cly2fnimcg0u.ap-south-1.rds.amazonaws.com:3306/demo?useSSL=false" --changeLogFile=db.changelog.xml  --username=$DB_CREDS_USR --password=$DB_CREDS_PSW'
	  }
    } */
    stage('Update') {
      steps {
        sh 'sudo liquibase update --url="jdbc:mysql://demo.cly2fnimcg0u.ap-south-1.rds.amazonaws.com:3306/demo?useSSL=false" --changeLogFile=db.changelog.xml --username=$DB_CREDS_USR --password=$DB_CREDS_PSW'
      }
    }
  }
}
