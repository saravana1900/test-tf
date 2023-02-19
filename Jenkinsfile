pipeline{
    agent any
    
    parameters {

        string(name: 'CLIENT_NAME', defaultValue: '', description: 'Client Name')
        string(name: 'VPC_RANGE', defaultValue: '', description: 'Whether to manage vpc cidr range')
        string(name: 'RUN_TYPE', defaultValue: 'plan', description: 'Terraform Run Type. For example "plan" or "apply".')
        string(name: 'ENVIRONMENT', defaultValue: 'prod', description: 'This could be dev, sit, uat or prod')
        string(name: 'DEPLOYMENT_REGION', defaultValue: 'us-east-1', description: 'Region')
        booleanParam(name: 'USERINPUT', defaultValue: true, description: 'Deploy User Input for terraform')
        booleanParam(name: 'VPC', defaultValue: false, description: 'Whether to manage customer vpc')
        booleanParam(name: 'KMS', defaultValue: false, description: 'Whether to manage customer managed key')
        booleanParam(name: 'KEY_PAIR', defaultValue: false, description: 'Whether to manage key pair')
        booleanParam(name: 'SG', defaultValue: false, description: 'Whether to manage security groups')
        booleanParam(name: 'EC2', defaultValue: false, description: 'Whether to manage EC2')
        booleanParam(name: 'LINUXDBM', defaultValue: false, description: 'Whether to manage EC2')
        booleanParam(name: 'RAPID7', defaultValue: false, description: 'Whether to manage EC2')
        booleanParam(name: 'PLAYBOOK', defaultValue: false, description: 'Whether to manage EC2')
        booleanParam(name: 'RESOURCES', defaultValue: false, description: 'New Resources created')
    }

    stages {
        stage('INPUTVALUES') {
       		when {

         		expression { params.USERINPUT == true }
       		
            }
            steps {
                  script {
                    sh '''

             			                         
                          echo " Environment is       :  $ENVIRONMENT"
                          echo " VPC is               :  $VPC_RANGE"
                          echo " Deployment Region is :  $DEPLOYMENT_REGION"
                          echo " Client is            : $CLIENT_NAME"   
                          echo " User Input           : $USERINPUT"
                          ls /usr/local/bin
                    '''
           		    }
            }
        }

    }
}