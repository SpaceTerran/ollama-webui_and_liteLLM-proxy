# Ansible Playbook for Deploying ollama-webui and liteLLM-proxy - Azure OpenAI

This ansible playbook helps to automate the deployment of two containers, `ollama-webui` and `liteLLM-proxy` using Docker. It also enables integration with Azure Cognitive Services - OpenAI.

## Prerequisites
To use this playbook, you are expected to have Ansible installed on your local/remote machine, as well as Docker.

## Secrets File
This playbook requires a secret file containing your Azure API details. Create a YAML file named `secrets.yml` with the following structure:

```yml
AZURE_API_KEY: "xxxxxxxxxxxxxxxxxxxxxxxxxxxxxx"
AZURE_API_BASE: "https://yourEndpoint.openai.azure.com"
AZURE_API_VERSION: "2023-05-15"
```
**Note:** Please replace the placeholders with your actual Azure API details.

## Ansible Playbook Details
The playbook covers different tasks including cloning the repository, checking for required directories and creating them if they don't exist, and deploying the docker containers.

### Variable Configuration
Make sure to customize the following `vars` as per your environment:

- `nfs_server`: IP address of your NFS server.
- `nfs_path`: Path to your NFS share.
- `container_name`: Docker-compose stack name.
- `docker_compose_dir`: Directory to store docker-compose files. Ensure this directory exists before running the playbook.
- `ansible_python_interpreter`: Path to your Python interpreter.

## Running the Ansible Playbook
You can run the playbook using the following command:

```bash
ansible-playbook playbook_name.yml --ask-vault-pass
```
Replace `playbook_name.yml` with the name of your playbook file.

## Disclaimer
The playbook runs tasks as root. While that might be acceptable in a demonstration or testing environment, it is a significant security risk in production. This playbook should, therefore, be used for demonstration purposes only.

Have a good look at the playbook and adjust according to your environment and requirements before running it.
