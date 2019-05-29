Ansible Role: Build Git from source
=========

An ansible role to build a git version from source code for Linux based systems.

Requirements
------------

The role targets Linux systems.

It will install git from source code and prepend the system path with the installed version.

- Works with systems behind proxy servers
- Validates checksum after fetching the source code archive

Git will be installed under: `/usr/src/git-{{git_version}}`.
The system's `PATH` variable will be prepended with the location, defined in: `/etc/profile.d/git-path.sh`

_Note:_ The role requires `become` features enabled.

Role Variables
--------------

Optional:

```yaml
git_version: "2.21.0" # A valid git version

git_proxy_env: { # Override if needed
  no_proxy: ""
}
```

If you are behind a proxy, you may override the `git_proxy_env` with a list of proxy environment variables.

Dependencies
------------

None

Example Playbook
----------------

```yaml
    - hosts: localhost
      roles:
        - role: nioniosfr.git_source # ansible-galaxy

        - role: ansible-role-git-source # github clone
```

License
-------

MIT

Author Information
------------------

[NioniosFr](https://github.com/NioniosFr)
