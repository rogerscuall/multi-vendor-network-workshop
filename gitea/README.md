
# Objective

This exercise will set up your environment for the remaining demos included in this repository. This exercise includes steps to set up a version control system, which is used to track and provide control over changes made to the automation code. Version control (sometimes called source control) plays an important role in any development project, including automation development. This repository will be used with both the command line utilities and when we use the Ansible Automation Platform.

# Diagram

![Red Hat Ansible Automation](https://github.com/ansible/workshops/raw/devel/images/ansible_network_diagram.png)

# Guide

## Step 1 - Connecting via VS Code

<table>
<thead>
  <tr>
    <th>You must use Visual Studio Code to setup the demos. Visual Studio Code provides:
    <ul>
    <li>A file browser</li>
    <li>A text editor with syntax highlighting</li>
    <li>A in-browser terminal</li>
    </ul>
    Direct SSH access is available as a backup, or if Visual Studio Code is not sufficient to the student.  There is a short YouTube video provided if you need additional clarity: <a href="https://youtu.be/Y_Gx4ZBfcuk">Ansible Workshops - Accessing your workbench environment</a>.
</th>
</tr>
</thead>
</table>

- Connect to Visual Studio Code from the Workshop launch page (provided by Red Hat RHDP).  The password is provided below the WebUI link.

  ![launch page](images/launch_page.png)

- Type in the provided password to connect.

  ![login vs code](images/vscode_login.png)


## Step 2 - Using the Terminal

- Open a terminal in Visual Studio Code (VSC):

  ![picture of new terminal](images/vscode-new-terminal.png)

## Step 3 - Deploy Gitea on the Control Node

We are going to run our first playbook here, which will deploy a Gitea server in a container on the control node (ansible-1).

In the VSC terminal, use wget to download the gitea.yml file, and then use `ansible-navigator` to run the playbook.
```
wget https://gitlab.com/redhatautomation/multi-vendor-network-workshop/-/raw/main/gitea/gitea.yml
```
You can run the ansible-navigator command with low verbosity, or if you want to see more of what Ansible is doing, you can add `-v` (up to 4 v's) to the ansible-navigator command.
```bash
ansible-navigator run -m stdout gitea.yml
or 
ansible-navigator run -m stdout gitea.yml -v

```
Running the gitea.yml playbook will output to the terminal all of the tasks that are done to deploy the Gitea container, configure it for use in the environment, and setup the network-demos-repo that we will be working out of.  When the playbook has finished running, you should be able to change into the network-demos-repo directory and run git status to see that we are up today.
```
cd network-demos-repo
git status
```

## Step 4 - Open the project directory in Visual Studio Code

Click on the files icon in the upper right corner of your Visual Studio Code window, and click `Open Folder`.

![picture of open folder](images/open_folder.png)

In the pop-up window, choose the `/home/student/netowrk-demos-repo` folder, and select `OK`.

