pipeline {
    agent any
    environment {
        KUBECONFIG = '/Users/Lenovo/.kube/config'
    }
//First stage checks if a namespace wp exist and if not it creates one    
    stages {
         stage('Check or Create Namespace') {
            steps {
                script {
                    def namespace = 'wp'
                    def namespaceExists = bat(returnStatus: true, script: "kubectl get namespace ${namespace}")
                    
                    if (namespaceExists == 0) {
                        echo "Namespace '${namespace}' exists."
                    } else {
                        echo "Namespace '${namespace}' does not exist. Creating..."
                        bat "kubectl create namespace ${namespace}"
                    }
                }
            }
        }
        
//Checking if we have heml chart deployed and if not we are deploying
    
        
        stage('Check and Install WordPress') {
            steps {
                script {
                    def chartName = 'wordpress'
                    def releaseName = 'final-project-wp-scalefocus'
                    def chartInstalled = bat(
                        script: "helm list -q ${releaseName}",
                        returnStatus: true
                    )
                    
                    if (chartInstalled != 0) {
                        echo "WordPress chart not installed. Installing..."
                        bat "helm install ${releaseName} /Users/Lenovo/Desktop/finally/charts/bitnami/wordpress -n wp -f /Users/Lenovo/Desktop/finally/charts/bitnami/wordpress/values.yaml"
                        
                        echo "Waiting for the WordPress pod to be ready..."
                    } else {
                        echo "WordPress chart is already installed."
                    }
                }
            }
        }
//Forwarding to port 80:80 for wordpress        
        stage('Wait and run pods') {
            steps {
                echo "Waiting for 1 minute..."  //Like a timer for 1min before forwarding to port because it takes some time to get the pods up and running 
                sleep time: 60, unit: 'SECONDS'
                echo "Wait complete."
                
                echo "Forwarding port to the WordPress service..."
                bat "kubectl port-forward --namespace wp svc/final-project-wp-scalefocus-wordpress 80:80" //We have a wordpress user's blog :)
            }
        }
        
        
    }
}
