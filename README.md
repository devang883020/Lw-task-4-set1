# Lw-task-4-set1
Scenario : Create a ConfigMap and Use it in a
 Deployment.


I'd create a ConfigMap with the custom HTML content and set up an Nginx deployment to serve it.
Let me break this down into steps.

To deploy this solution, follow these steps:

Apply the ConfigMap and Deployment:

kubectl apply -f configmap.yaml

kubectl apply -f deployment.yaml

Key points about the solution:

The ConfigMap contains two items:

The custom HTML page
A custom nginx.conf to serve the HTML page as the index


The Deployment:

Uses nginx:latest image
Mounts both the custom HTML page and nginx configuration
Uses subPath to mount individual files instead of entire directories
Configures the container to serve the custom page on port 80


To verify the deployment:


kubectl get pods

# Create a port-forward to test locally
kubectl port-forward deployment/nginx-custom 8080:80
Then you can access the custom page at http://localhost:8080 


