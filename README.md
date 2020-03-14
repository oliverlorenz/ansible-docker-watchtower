# ansible-docker-watchtower

installs [watchtower](https://hub.docker.com/r/v2tec/watchtower/) as docker container

## usage example

```
  - name: ensure watchtower is running
    import_role:
      name: docker-watchtower
    vars:
      webhook_url:
      docker_registry_logins:
        - registry: https://gcr.io
          username: _json_key
          password: " {{ lookup('file', 'files/google-auth.json')}}"
      docker_env_vars:
        WATCHTOWER_NOTIFICATIONS: slack
        WATCHTOWER_NOTIFICATION_SLACK_HOOK_URL: "https://server/webhooks/watchtower"
        WATCHTOWER_NOTIFICATION_SLACK_IDENTIFIER: "{{ ansible_hostname }}"

```
