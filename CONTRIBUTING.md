# Contributing to RHEL 9 DISA STIG Hardening Role

Thank you for your interest in contributing to the RHEL 9 DISA STIG Hardening Role! Your contributions help make our project better and more secure. Please take a moment to review the guidelines below to ensure a smooth collaboration process.

## Table of Contents

- [Code of Conduct](#code-of-conduct)
- [How to Contribute](#how-to-contribute)
  - [Reporting Issues](#reporting-issues)
  - [Suggesting Enhancements](#suggesting-enhancements)
  - [Submitting Pull Requests](#submitting-pull-requests)
- [Development Guidelines](#development-guidelines)
  - [Repository Structure](#repository-structure)
  - [Coding Style and Best Practices](#coding-style-and-best-practices)
  - [Testing](#testing)
- [Commit Messages](#commit-messages)
- [License](#license)

## Code of Conduct

Please note that this project adheres to a [Code of Conduct](CODE_OF_CONDUCT.md). By participating, you are expected to uphold this code. Please report unacceptable behavior to [github@mail.redkey.sh](mailto:github@mail.redkey.sh).

## How to Contribute

There are several ways you can contribute to this project:

### Reporting Issues

If you find a bug or have a security concern, please:
1. Check the [issue tracker](https://github.com/redkeysh/ansible-rh-stig/issues) to see if it has already been reported.
2. Open a new issue with a clear and descriptive title.
3. Provide as much detail as possible (steps to reproduce, expected vs. actual behavior, etc.).

### Suggesting Enhancements

If you have ideas for improvements or new features:
1. Search the issue tracker for similar enhancement proposals.
2. Open a new issue and label it as "enhancement."
3. Describe your suggestion clearly, explaining its benefits and any potential drawbacks.

### Submitting Pull Requests

When you’re ready to contribute code:
1. Fork the repository.
2. Create a new branch for your changes:
```
git checkout -b feature/my-new-feature
```
3.  Make your changes following the guidelines below.
    
4.  Ensure that your code adheres to our coding style.
    
5.  Test your changes locally.
    
6.  Commit your changes with clear commit messages.
    
7.  Push your branch to your fork and open a pull request.
    
8.  Describe your changes and reference any relevant issues.
    

## Development Guidelines

### Repository Structure

Our repository is organized as follows:

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
└── CONTRIBUTING.md     
```

### Coding Style and Best Practices

-   **Modularity:**  
    Keep tasks modular. Break tasks into separate files by category (audit, SSH, firewall, etc.).
    
-   **Variable Usage:**  
    Use global default variables defined in `defaults/main.yml` for consistency.
    
-   **Idempotence:**  
    Ensure tasks are idempotent. Running the playbook multiple times should not cause unintended changes.
    
-   **Comments and Banners:**  
    Include clear header banners in tasks to indicate which DISA STIG control each task addresses.
    

### Testing

-   Run your changes against the test playbook in the `tests/` directory.
    
-   Use tools like `ansible-lint` to check for syntax and best practices.
    
-   Document any new tests or steps needed to verify your changes.
    

## Commit Messages

Please use clear, descriptive commit messages.

```
<type>(<scope>): <subject>

<body>

```

Where:

-   **type:** feat, fix, docs, style, refactor, test, chore.
    
-   **scope:** Affected module or component (e.g., audit, ssh).
    
-   **subject:** A brief summary of the change.
    

Example:

```
fix(audit): correct rule for tracking /var/log/tallylog changes

Updated the audit rule to properly track changes in /var/log/tallylog as per DISA STIG requirements.

```

## License

This project is licensed under the GNU-GPLv3.0 License. See the LICENSE file for details.

----------
We appreciate your contributions! If you have any questions, please open an issue or contact the maintainers.
