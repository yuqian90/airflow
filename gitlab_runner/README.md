# Instructions on setting up GitLab runner on Kubernetes (GKE)

* Configure gcloud tool (https://cloud.google.com/sdk/install)
* Configure your project_id, cluster name and other parameters in [_config.sh](_config.sh)
* Create cluster in GKE by running [create_cluster.sh](create_cluster.sh)
* Run [install_rbac.sh](install_rbac.sh) to install tiller service account
* Copy [runner-registration-token-template.yaml](runner-registration-token-template.yaml) to
  [runner-registration-token.yaml](runner-registration-token.yaml)
* Add token available at your Settings -> CI/CD -> Runners page in 
  [runner-registration-token.yaml](runner-registration-token.yaml)
* Disable Shared Runners in Settings -> CI/CD -> Runners page
* Install runner on your : [./install_runner.sh](./install_runner.sh)
* Check that the runner is registered in Settings -> CI/CD -> Runners page

That's it. You should have GitLab Runner up and running.

Later when you need to update the runned (because of changes to [values.yaml](value.yaml)) use
[./upgrade_runner.sh](upgrade_runner.sh)
