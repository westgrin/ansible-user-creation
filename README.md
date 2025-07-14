# Mini Project - Automate User Creation on Linux Server using Ansible

## Project Overview
This project automates user creation on an Ubuntu server (54.227.3.228) using an Ansible playbook, configuring groups and SSH access. Builds on previous Ansible and Terraform projects (Jul 8-14, 2025).

## Setup
- Initiated on Jul 14, 2025, 12:07 PM WAT.
- Used WSL Ubuntu, VS Code, and Git Bash in `C:\Users\Abraham\Documents\Workspace\ansible-user-creation`.
- System: 2 CPUs, 2GB free memory, 20GB free disk space.
- Target: AWS EC2 instance (Ubuntu 22.04, IP: 54.227.3.228).

## Execution Steps
1. **Confirm Prerequisites**:
   - Verified Ansible and SSH access to `ubuntu@54.227.3.228`.
   - Generated SSH keys for `user1` and `user2`.
   - [Screenshot: `ansible_version_output_local.png` - Shows Ansible version.]
   - [Screenshot: `ssh_access_output_local.png` - Shows SSH to target.]
   - [Screenshot: `ssh_user_keys_output_local.png` - Shows user SSH keys.]
2. **Set Up Inventory**:
   - Created `inventory.ini` for Ubuntu target.
   - [Screenshot: `ansible_ping_output_local.png` - Shows ping response.]
3. **Create Playbook**:
   - Wrote `create_users.yml` to create `user1` (sudo group) and `user2` (docker group) with SSH keys.
   - [Screenshot: `ansible_playbook_output_local.png` - Shows playbook content.]
4. **Run Playbook**:
   - Executed `ansible-playbook` to create users.
   - [Screenshot: `ansible_playbook_run_output_local.png` - Shows playbook run.]
5. **Verify Users**:
   - Checked `/etc/passwd`, `/home`, and SSH access for `user1` and `user2`.
   - [Screenshot: `user_verification_output_local.png` - Shows user creation.]
   - [Screenshot: `ssh_user_access_output_local.png` - Shows SSH logins.]
6. **Side Hustle Task**:
   - Automated playbook with GitHub Actions.
   - Pushed to `https://github.com/westgrin/ansible-user-creation`.
   - [Screenshot: `github_actions_ansible_run_local.png` - Shows workflow run.]
7. **Clean Up (Optional)**:
   - Created `cleanup_users.yml` to remove users.
   - Destroyed EC2 instance (if applicable).
   - [Screenshot: `terraform_destroy_output_local.png` - Shows destroy output.]

## Learning Summary
This project advanced my Ansible skills, building on my previous setup (Jul 14, 2025). It reinforced playbook creation, group management, and SSH key configuration, aligning with my DevOps goals (June 16, 2025).

## Tools Used
- **WSL Ubuntu Terminal**: For Ansible and SSH commands.
- **VS Code**: For editing playbooks and `README.md`.
- **Git Bash**: For GitHub operations.
- **GitHub Actions**: For automation.
- **Ansible**: For user creation automation.
- **Terraform**: For target node creation (optional).

## Project Deliverables
- **Documentation**: This `README.md` with steps and learning summary.
- **Screenshots**:
  - `ansible_version_output_local.png`
  - `ssh_access_output_local.png`
  - `ssh_user_keys_output_local.png`
  - `ansible_ping_output_local.png`
  - `ansible_playbook_output_local.png`
  - `ansible_playbook_run_output_local.png`
  - `user_verification_output_local.png`
  - `ssh_user_access_output_local.png`
  - `github_actions_ansible_run_local.png`
  - `terraform_destroy_output_local.png` (if applicable)
- **Script Link**: [GitHub Repository](https://github.com/westgrin/ansible-user-creation)

## Local Development Instructions
1. Clone repository: `git clone https://github.com/westgrin/ansible-user-creation.git`
2. Install Ansible: `sudo apt install ansible -y`
3. Set up SSH keys: `ssh-keygen` for `user1` and `user2`
4. Configure inventory: Edit `inventory.ini` with target details
5. Run playbook: `ansible-playbook -i inventory.ini create_users.yml`
6. Verify users: Check `/etc/passwd` and test SSH access

## Troubleshooting
- Ensured SSH access with `ssh ubuntu@54.227.3.228`.
- Fixed playbook errors by verifying `inventory.ini` and SSH key paths.
- Set DNS to `8.8.8.8` for network issues.
- Verified system resources with `lscpu`, `free -h`, `df -h`.
- Ensured target security group allows port 22.

## Conclusion
This project successfully automated user creation on an Ubuntu server using Ansible, enhancing my automation skills for DevOps tasks.