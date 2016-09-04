# Ansible Role: Dotfiles

[![Build Status](https://travis-ci.org/ymajik/ansible-role-dotfiles.svg?branch=master)](https://travis-ci.org/ymajik/ansible-role-dotfiles)

Installs dotfiles from a given Git repository.

## Requirements

Requires `git` on the managed machine.

## Role Variables

Available variables are listed below, along with default values (see `defaults/main.yml`):

    dotfiles_repo: "https://github.com/ymajik/dotfiles.git"

The git repository to use for retrieving dotfiles. Dotfiles should generally be laid out within the root directory of the repository.

    dotfiles_repo_accept_hostkey: no

Add the hostkey for the repo url if not already added. If ssh_opts contains "-o StrictHostKeyChecking=no", this parameter is ignored.

    dotfiles_repo_local_destination: "~/Documents/dotfiles"

The local path where the `dotfiles_repo` will be cloned.

    dotfiles_home: "~"

The home directory where dotfiles will be linked. Generally, the default should work, but in some circumstances, or when running the role as sudo on behalf of another user, you may want to specify the full path.

    dotfiles_files:
      - .bash_aliases
      - .bashrc
      - .gitconfig
      - .gitignore
      - .vimrc

Which files from the dotfiles repository should be linked to the `dotfiles_home`.

## Dependencies

None

## Example Playbook

    - hosts: localhost
      roles:
        - { role: ymajik.dotfiles }

## License

BSD

## Author Information

ymajik
