#!/user/bin/env groovy
import hudson.model.*
import hudson.EnvVars
import java.net.URL

node{
    stage('Git Checkout') {
        git 'https://github.com/saiwebaditya/DevOpsClassCodes.git'
    }
    stage('Compile Addressbook') {
      withMaven(maven: 'MyMaven') {
      sh 'mvn compile'
      }
    }
    stage('package') {
        withMaven(maven: 'MyMaven') {
            sh 'mvn package'
        }
    }
}
