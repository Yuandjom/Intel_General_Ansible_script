# Intel General AI Environment Setup

This repository hosts an Ansible playbook, `setup-general.yml`, meticulously crafted to streamline the establishment of a general AI environment, specifically tailored for Intel architectures. This playbook facilitates the installation of Miniconda, orchestrates the creation of a Conda environment named `Intel_AI`, and manages the deployment of a suite of packages and tools, including TensorFlow, PyTorch, and various Intel extensions.

For more insights into Intel's AI tools and their optimization capabilities, visit the [Intel AI Tools Selector](https://www.intel.com/content/www/us/en/developer/tools/oneapi/ai-tools-selector.html).

## Prerequisites

To utilize this playbook effectively, ensure the following prerequisites are met:

- Ansible is installed on your control node, the system from which you'll execute the playbook.
- You have SSH access to all target nodes, the machines destined for the AI environment setup.
- You possess adequate permissions for installing packages and performing system modifications on the target nodes.

## Configuration

This playbook is designed with flexibility in mind, using variables that can be tailored to your specific requirements:

- `workspace_path`: Defines the path for creating the workspace directory.
- `conda_installer_url`: URL for downloading the Miniconda installer.
- `conda_env_file`: Local path of the Conda environment file.
- `remote_conda_env_file`: Destination path on the remote node for the Conda environment file.
- `conda_path`: The installation path for Miniconda.

## Running the Playbook

Execute the playbook by following these steps:

1. Clone the repository:
   ```bash
   git clone https://github.com/YOUR_GITHUB/YOUR_REPOSITORY.git
   cd YOUR_REPOSITORY
   ```


## Configuration

The playbook uses several variables that you can customize according to your needs:

- `workspace_path`: The directory path for creating a workspace.
- `conda_installer_url`: The URL for the Miniconda installer.
- `conda_env_file`: The local path to the Conda environment file.
- `remote_conda_env_file`: The remote path where the Conda environment file will be copied.
- `conda_path`: The installation path for Miniconda.

## Running the Playbook

To run the playbook, follow these steps:

1. Clone the repository:

   ```bash
   git clone https://github.com/YOUR_GITHUB/YOUR_REPOSITORY.git
   cd YOUR_REPOSITORY
   ```
Customize the variables in setup-general.yml as needed.
Run the playbook:
```bash
ansible-playbook -i hosts.ini setup-general.yml 
```

## Components Installed

The playbook performs the following tasks:
- Installs Git and finds the Git executable path.
- Creates the specified workspace directory.
- Installs Miniconda and sets it up.
- Copies the Conda environment file and creates a Conda environment.
- Installs gperftools and configures it.
- Gathers CPU architecture information.
- Checks versions of PyTorch and Intel Extension for PyTorch.

## Conda Environment
The Conda environment, as defined in ```env/Intel_AI.yml```, includes:
- Python (python=3.10)
- TensorFlow (tensorflow=2.14) 
- Intel Extension for TensorFlow (intel-extension-for-tensorflow=2.14)
- Intel Optimization for Horovod (intel-optimization-for-horovod=0.28.1.1)
- PyTorch (pytorch=2.0.1)
- Intel Extension for PyTorch (intel-extension-for-pytorch=2.0.100)
- OneCCL Bindings for PyTorch (oneccl_bind_pt=2.0.0)
- Torchvision (torchvision=0.15.2)
- Jemalloc

## Notes
- Ensure you have the necessary permissions to run the playbook and make changes on the target machines.
- The setup process might take a significant amount of time, depending on network speed and the computational capabilities of the target machine.

