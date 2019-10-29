node {
    def app

    stage('Clone repository') {
        /* repository cloned to our workspace */

        checkout scm
    }

    stage('Build image') {
        /* To builds the dockerimage */
        //update your ECR registry URI
        app = docker.build("532002947334.dkr.ecr.us-east-1.amazonaws.com/sample-microservice")
    }

    stage('Test image') {
        /* Try killing some white walkers for testing ;-) */

        app.inside {
            sh 'echo "Hurray !! Tests passed, Valar Morghulis "'
        }
    }

    stage('Push image') {
        /* Finally, we'll push the image */
        //docker.withRegistry('https://registry.hub.docker.com', 'docker-hub-credentials') {
        // update your ECR registry URI and jenkins crendential paramater
        docker.withRegistry('532002947334.dkr.ecr.us-east-1.amazonaws.com/sample-microservice', 'eyJwYXlsb2FkIjoia25FR2tNU05ZVEZXUXpqUWVXVlZyR2wrR2tWRTlpME56b2NlbVViQWUvTnZhUFhwUFU4WkN2OTJBZWVmcGlVS0xsK1VGRVRiUkJXQ1RNRXErOWJQOWFDOGFWcEdBY0dnRVdQZkJYd0Q2bmllMC9hRnhvRXRzUENhVGZvY0U2MmxLK3QvbllsdGhLejJqL25hbXJWODMwYWZiTE9XYXVVVWd5V1lxaHBiQVNEZVRzQ1k1Y1E5ZU5DbEVha3RZdXJ2N1lnOWlGRFI1Q2M4c2UyOThMU0hzcHJGYk9zZHVIK1YrcDlqSEwwL0I0MUM0dlkzK3R5dGVKbjVsUnVyR1hNdVd2VUEzWU0vaFg0LytVbDFVR0dSSGU3R3puUEY5b015NmVhNXQ5VEpPc0RBdFowaE4rVkpTVjNHcnpJMU9xTXhISjV6QUVzeWR3b1BRN0NDRWlKYUlSaTZTOHFWWXQvYnFMbDBaU0IzODdVdDNManBxaU9Gc0o2bndIaVpLdkZEQlRXcUFuMTg2SWdnOTZLY0luejF3Y0p4STl5TnlqZ2V5eE9ncEdqbEVoQStlWEZPMlRFUTRWZjg4ZnVzak9PVDNzNFB3d1NKTDFGN0dxN0ljaHFqUXFxUVk4OWMzeU1OVEZPM1N6VXBQR3luOHN6NUFNTmdhQWNjOHpTVCtTZkdJbmlFTXBnSzlkeCt2ckZrNW43d3YwUEJ3a1p4ZmhxTnRwNlBDNUd3M2ZNcExlcGhISlhXRVkwWkFObWtBbVdSNmRXaXo3WDRNNzdWYmxxQm4rYURhWGwwcHJRcmlNTWJzWnlpMjM3MWxBNW8xRWRlR3dpVUxuV3lBRXY2eWZVSlRnUE1qUWlQbGs2VUdDT1Z0SWVYTTdVU3kxVUlkM0lZMTB1cjRhTjNseXhiSEs5VFhXTjlGcGdZOW8zS0lDS0NUdnllZjlqSzE2MEVVcGhDdnpOOXc1MjRlTGVNVUJyNEg2MkMwZmZISWNDSzlkeXlQWStmekNnT2JJRm9MeHRnT0xVZFN2R3ZUYmgwc0c1SCtuT2xlbHFSd0xZR21Fcis1Rm8yTllRVDlpdmZzV1hHckxNZHd0SldER2J5NzNGZENleUFQaHo4YnVmd01NdHZqZFUxK2hXWExieHJnSmI1cmJoZHdreDlyMW4wbW91K09IK0RRd0YzUUhNM2Y5YmFzN1JCVEZXR2FVQjZQV1NKZ0NmcEVZalBhUUNTbnRsbWVIUG9Ea1hsbk1valRuemFZdUlUSlB2ZkRZY0NENGthNnlKUzkrVzluc1hRWC9QelRYS1pDdVdxRmtZcHJ1ZWtFK3dRZXdVZWNvZERDS2xMNUhDTUFtc2wyR2MvckNjWFRHcTY2dnRDd1BtY2NRQjRTdzliU2xsU2lHUmt6RVlETWszTlN0VXFoV2svUDZ6ck1wTktJSjlUUENwY1dTMVI0MEtWbU9WRG9zcUZDVWwyclFZTmNTcXpLZ2pobFVWMU45M05xMmUreE5EL3ZnPT0iLCJkYXRha2V5IjoiQVFFQkFIaHdtMFlhSVNKZVJ0Sm01bjFHNnVxZWVrWHVvWFhQZTVVRmNlOVJxOC8xNHdBQUFINHdmQVlKS29aSWh2Y05BUWNHb0c4d2JRSUJBREJvQmdrcWhraUc5dzBCQndFd0hnWUpZSVpJQVdVREJBRXVNQkVFRE9hdmhVVFlWQUVBaE5zbEdnSUJFSUE3aXgyeVUvdTVvU1NHNFd5RURBSE1FZGpPLzRzbnhFQlFpeFdaRVVyajYxdTdMK1VMR0RYYnV1cFk1cFVMVHpMNnZBSVBOTm0yWWVBWW16Zz0iLCJ2ZXJzaW9uIjoiMiIsInR5cGUiOiJEQVRBX0tFWSIsImV4cGlyYXRpb24iOjE1NzI0MDY4NDF9')    {
            //app.push("${env.BUILD_NUMBER}")
            app.push("latest")
        }
    }
}
