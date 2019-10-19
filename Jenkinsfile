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
    stage('Review Addressbook'){
        withMaven(maven: 'MyMaven'){
            sh 'mvn pmd:pmd'
        }
    } 
    stage('Coverage Report of Addressbook'){
        withMaven(maven: 'MyMaven'){
            sh 'mvn cobertura:cobertura -Dcobertura.report.format=xml'
        }
    }
    stage('Test Addressbook'){
        withMaven(maven: 'Mymaven'){
            sh 'mvn test'
        }
    }
    stage('package') {
        withMaven(maven: 'MyMaven') {
            sh 'mvn package'
        }
    }
}
