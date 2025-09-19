Step 1: Project setup
# Create project folder
mkdir ~/my-k8s-project
cd ~/my-k8s-project

# Initialize Git
git init

Step 2: Save YAML file

Create your webserver.yaml file in this folder (using your editor).

Step 3: Add and commit files locally
# Add all files
git add .

# Commit changes with a message
git commit -m "Add webserver pod with sidecar logging"

Step 4: Connect to GitHub via SSH
# Remove wrong remote (if any)
git remote remove origin

# Add correct SSH remote
git remote add origin git@github.com:arum5123/k8s-tasks.git

Step 5: Push to GitHub

If your branch is main:

git push -u origin main


If your branch is master:

git push -u origin master

Step 6: Kubernetes commands
# Apply the YAML file to create Pod
kubectl apply -f webserver.yaml

# Check Pods status
kubectl get pods

# Describe Pod for details
kubectl describe pod webserver

# Check logs from sidecar container
kubectl logs webserver -c sidecar-container

# Check logs from nginx container
kubectl logs webserver -c nginx-container

# Port forward to test Nginx in browser
kubectl port-forward pod/webserver 8080:80

Step 7: Updating your GitHub repo later
# Add any new or updated files
git add .

# Commit with a descriptive message
git commit -m "Update YAML / add commands"

# Push changes to GitHub
git push

Optional: View all branches
# Local branches
git branch

# Remote branches
git branch -r

# All branches
git branch -a
