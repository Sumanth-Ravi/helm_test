# Simple NGINX app with Helm

A minimal repository for testing Helm deployment from GitHub.

## Application Deploy UI values
- Deployment Type: Helm Chart
- Deployment Method: Git Repository
- Release Name: `github-nginx-test`
- Repository URL: `https://github.com/YOUR_GITHUB_USERNAME/YOUR_REPOSITORY.git`
- Branch / Tag: `main`
- Chart Path: `charts/simple-nginx`
- Authentication: leave blank for a public repo; use your organization's approved method for private repos.
- Namespace: choose an existing namespace, e.g. `oct26test` if available.

Replace the username and repository placeholders with your actual GitHub repository URL.

## Repository structure
```text
README.md
charts/
  simple-nginx/
    Chart.yaml
    values.yaml
    templates/
      deployment.yaml
      service.yaml
      NOTES.txt
```

## Verify (from a Kubernetes-connected terminal)
```bash
kubectl get pods -n oct26test -o wide
kubectl get deployments -n oct26test
kubectl get services -n oct26test
```

This chart deploys one NGINX replica behind a ClusterIP service. Kubernetes normally schedules it to an eligible worker node. Downloading this ZIP does not create a GitHub repository; upload these files to a repository in your GitHub account.
