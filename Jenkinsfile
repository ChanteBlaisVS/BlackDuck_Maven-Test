node ('docker2'){

def customImage;
    
    stage ('Checkout SCM') {
        checkout scm        
    }
    
    stage ('Build Image') {
        //customImage = docker.build("acme:test")
    }   
        
    stage ('Black Duck Scan') {
         sh """
         export DETECT_LATEST_RELEASE_VERSION=4.1.0
         curl -O https://artifactory.core.rcsops.com/artifactory/hub-detect/hub-detect-virtustream.sh
         chmod +x hub-detect-virtustream.sh && ./hub-detect-virtustream.sh --blackduck.hub.url='https://bduck01.core.rcsops.com' --blackduck.hub.proxy.host=10.131.146.14 --blackduck.hub.proxy.port=3128 --blackduck.hub.api.token=N2E2MDkyODktNGZlNi00ZmNiLThhNDUtM2I5M2NmNjhiNTkwOmE3ZTBlYzAwLTRjOWEtNDhlNS1hNDkxLWE1ZjcwOWE3YzU1NA== --detect.project.version.name=1.0 --detect.project.name=Maven_Test --detect.code.location.name="maven_test-1.0" --detect.project.codelocation.delete.old.names=true
         """    
     }
   
}
