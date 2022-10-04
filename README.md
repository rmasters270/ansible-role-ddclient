# DDClient

Install DDClient container on a Kubernetes cluster for updates to Cloudflare and Google Domains.

[![Ansible Galaxy](https://img.shields.io/badge/ansible--galaxy-ddclient-blue.svg)](https://galaxy.ansible.com/rmasters270/ddclient)

## Requirements

### Localhost

The role is intended to run from the Ansible controller.  If the playbook is executed on a different host it will fail because the templates must be copied to the target host.

### Kube Config

The host and user running the playbook must have kube config configured.

## Role Variables

| Variable                | Required | Default                            | Comments                                    |
|-------------------------|----------|------------------------------------|---------------------------------------------|
| ddclient_namespace      | yes      | ddclient                           | Kubernetes namespace                        |
| ddclient_image_tag      | yes      | v3.9.1-ls100                       | [tags](https://github.com/linuxserver/docker-ddclient/tags) |
| cloudflare_email        | no       | user@example.com                   | Cloudflare email address                    |
| cloudflare_key          | no       | Your-Cloudflare-APIKey             | Cloudflare API Key                          |
| cloudflare_email        | no       | example.com                        | Cloudflare zone                             |
| googledomains_username  | no       | my-generated-user-name             | Random user name from Google Domains        |
| googledomains_password  | no       | my-generated-password              | Random password from Google Domains         |
| googledomains_host      | no       | my-generated-user-name             | Hostname for the                            |

## Dependencies

Setup `kube config` for the user account and host.

## Example Playbook

```yaml
- hosts: localhost

  roles:
    - rmasters270.ddclient
```

## License

MIT

## Author Information

Ryan Masters
