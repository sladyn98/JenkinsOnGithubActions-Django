node {
    // Copy this
    checkoutSource()

    // Write this on your own
    stage ("Install Application Dependencies") {
        sh '''
            apt-get update -y
            apt-get install python-pip -y
            pip install -r requirements.txt
           '''
    }

    stage ("Test Django APP") {
        sh '''
            python manage.py test
           '''
    }
}

// Copy all of this
def mysh(cmd) {
    sh('#!/bin/sh -e\n' + cmd)
}

def checkoutSource() {
  stage ('checkoutSource') {
    copyFilesToWorkSpace()
  }
}

def copyFilesToWorkSpace() {
  mysh "cp -r /github/workspace/* $WORKSPACE"
}

