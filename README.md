# aptly-client

This role configures a GPG key and a repository.
The key is expected to reside on a central host.

## Requirements

Debian

## Role Variables

| Name                        | Default / Mandatory        | Description                                         |
|:----------------------------|:--------------------------:|:----------------------------------------------------|
| `global_cache_dir`          | :heavy_check_mark:         | Path on the control machine where the key is cached |
| `aptly_client_aptly_host`   | :heavy_check_mark:         | Host from which to get the APT key                  |
| `aptly_client_key_location` | `/var/lib/aptly/aptly.asc` | GPG key location on the Aptly host                  |
| `aptly_client_repo`         | :heavy_check_mark:         | Repository to add to the client                     |

## Example Playbook

```yml
- hosts: slaves
  roles:
    - role: all
      global_cache_dir: "{{ lookup('env', 'HOME') }}/.cache/stuvus"
      aptly_client_aptly_host: aptly01
      aptly_client_repo: http://aptly.local/apt
```

## License

This work is licensed under a [Creative Commons Attribution-ShareAlike 4.0 International License](http://creativecommons.org/licenses/by-sa/4.0/).

## Author Information

- [Janne Heß](https://github.com/dasJ)
