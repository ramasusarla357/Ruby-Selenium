pipeline {
  agent any
  stages {
    stage('MI6_Informatica_Step1_SelectInputFile') {
      steps {
        echo 'Select Input file'
      }
    }
    stage('MI6_Informatica_Step2_CreatePwxReg') {
      steps {
        parallel(
          "MI6_Informatica_Step2_CreatePwxReg": {
            echo 'CreatePwxReg'
            
          },
          "MI6_Informatica_Step3_CreateTeraObjects": {
            echo 'CreateTeraObjects'
            
          }
        )
      }
    }
    stage('MI6_Informatica_Step4_CreatePowerCenterObjects') {
      steps {
        parallel(
          "MI6_Informatica_Step4_CreatePowerCenterObjects": {
            echo 'CreatePowerCenterObjects'
            
          },
          "MI6_Informatica_CreatePowerCenterDVO": {
            echo 'CreatePowerCenterDVO'
            
          },
          "MI6_Informatica_Step7_RefreshPowerCenterDVO": {
            echo 'RefreshPowerCenterDVO'
            
          },
          "MI6_Informatica_Step8_ImportTestPair": {
            echo 'ImportTestPair'
            
          }
        )
      }
    }
    stage('MI6_Informatica_Step5_UpdatePowerCenterPrmFile') {
      steps {
        echo 'UpdatePowerCenterPrmFile'
      }
    }
    stage('MI6_Informatica_Step9_PWCClientLoad') {
      steps {
        echo 'PwcClientLoad'
      }
    }
    stage('MI6_Informatica_Step10_EexecutePerpetualLoad') {
      steps {
        echo 'ExecutePerpetualLoad'
      }
    }
    stage('MI6_Informatica_Step11_ExecuteDVOTestPair') {
      steps {
        echo 'ExecuteDVOTestPair'
      }
    }
    stage('MI6_Informatica_Step12_CaptureDVOResults') {
      steps {
        echo 'CaptureDVOResults'
      }
    }
    stage('MI6_Informatica_Step13_CommittoSVN') {
      steps {
        echo 'CommitToSVN'
      }
    }
  }
}