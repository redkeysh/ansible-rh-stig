
# Red Hat 9 DISA STIG Hardening Ansible Role

## Overview

This repository contains a role and playbooks designed to harden Red Hat Enterprise Linux 9 in accordance with DISA STIG guidelines. The role focuses on configuring system settings, enforcing security policies, and remediating vulnerabilities outlined in the DISA STIG framework. It is intended to serve as a starting point for organizations looking to implement standardized or baseline security practices on their RHEL 9 systems.

## Features

- **Audit Configuration:** Ensures auditd is installed and configures log file sizes.
- **Password Policy Enforcement:** Implements password complexity and length requirements.
- **SSH Hardening:** Disables root login via SSH when enabled.
- **Firewall Management:** Verifies that firewalld is running and enabled.
- **Modular and Extensible:** Designed to be expanded with additional DISA STIG controls as needed.

## Requirements

- **Operating System:** Red Hat Enterprise Linux 9
- **Ansible Version:** 2.9 or later (tested with Ansible 2.10+)
- **Privileges:** Root or sudo privileges on target hosts

## Repository Structure

```
ansible-rh-stig/
├── assets/						# Folder containing default configuration files for external tools.
│   └── issue-banner.txt        
├── defaults/
│   └── main.yml                # Default configuration variables
├── handlers/
│   └── main.yml                # Handlers to restart services or apply changes
├── meta/
│   └── main.yml                # Role metadata and dependency information
├── tasks/
│   └── main.yml                # Main tasks to implement DISA STIG settings
│   └── audit.yml 				
│   └── filesystems.yml
│   └── firewall.yml
│   └── ...
├── playbook.yml                
├── README.md                   
└── LICENSE                     # Project license
```

## Installation

1. **Clone the Repository:**

   ```bash
   git clone https://github.com/redkeysh/ansible-rh-stig.git
   cd ansible-rh-stig
   ```

## Usage

### Applying the Role in a Playbook

Include the role in your Ansible playbook as shown below:

```yaml
---
- name: Harden RHEL 9 using DISA STIG guidelines
  hosts: all
  become: yes
  roles:
    - ansible-rh-stig
```

Run the playbook with:

```bash
ansible-playbook -i your_inventory playbook.yml
```

### Running Tests Locally

A test playbook is provided in the `tests/` directory. To run the tests locally:

```bash
ansible-playbook -i tests/inventory tests/test.yml
```

## Configuration

All configurable settings are located in the `defaults/main.yml` file. It is my goal to implemenet as many global variables as possible for full customization.

## Contributing

Contributions, issues, and feature requests are welcome! Please check the [CONTRIBUTING.md](CONTRIBUTING.md) file for guidelines on how to contribute to this project. When submitting changes, ensure that you adhere to the coding style and include tests for any new functionality.

## License

This project is licensed under the GPL-3.0 license. See the [LICENSE](LICENSE) file for details.

## Contact

For questions or additional information, please open an issue in this repository or contact the maintainer at [github@mail.redkey.sh](mailto:github@mail.redkey.sh).