# Configuration

There are 3 ways to configure Semaphore:

* [Snap configuration](https://snapcraft.io/docs/configuration-in-snaps)
* [Interactive setup](configuration.md#snap-configuration)
* [Configuration file](configuration.md#configuration-file)

### Snap configuration

Snap configurations should be used for when Semaphore was installed via Snap.

To see a list of available options, use the following command:

```bash
sudo snap get semaphore
```

You can change each of these configurations. For example if you want to change Semaphore port, use following command:

```bash
sudo snap set semaphore port=4444
```

Don't forget to restart Semaphore after changing a configuration:

```bash
sudo snap restart semaphore
```

### Interactive setup

Use this option for first time configuration (not working for Semaphore installed via Snap).

```bash
semaphore setup
```

### Configuration file

Semaphore uses a `config.json` configuration file with following content:

```javascript
{
  "bolt": {
    "host": "/home/ubuntu/semaphore.bolt",
  },
  "mysql": {
    "host": "localhost",
    "user": "root",
    "pass": "*****",
    "name": "semaphore",
    "options": {}
  },
  "postgres": {
    "host": "localhost",
    "user": "postgres",
    "pass": "*****",
    "name": "semaphore",
    "options": {}
  },
  "dialect": "postgres",
  "port": "",
  "interface": "",
  "tmp_path": "/tmp/semaphore",
  "cookie_hash": "*****",
  "cookie_encryption": "*****",
  "access_key_encryption": "*****",
  "email_sender": "",
  "email_host": "",
  "email_port": "",
  "web_host": "",
  "ldap_binddn": "",
  "ldap_bindpassword": "",
  "ldap_server": "",
  "ldap_searchdn": "",
  "ldap_searchfilter": "",
  "ldap_mappings": {
    "dn": "",
    "mail": "",
    "uid": "",
    "cn": ""
  },
  "telegram_chat": "",
  "telegram_token": "",
  "concurrency_mode": "",
  "max_parallel_tasks": 0,
  "email_alert": false,
  "telegram_alert": false,
  "slack_alert": false,
  "ldap_enable": false,
  "ldap_needtls": false
  "ldap_whoami": true
}
```

### Configuration options

| Configuration file      | Snap configuration      | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
|-------------------------|-------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `bolt.host`             | —                       | Path to the BoltDB database file                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| `mysql.host`            | `mysql.host`            | MySQL database host                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| `mysql.name`            | `mysql.name`            | MySQL database (schema) name                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| `mysql.user`            | `mysql.user`            | MySQL user name                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| `mysql.pass`            | `mysql.pass`            | MySQL user's password                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| `postgres.host`         | `postgres.host`         | Postgres database host                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| `postgres.name`         | `postgres.name`         | Postgres database (schema) name                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| `postgres.user`         | `postgres.user`         | Postgres user name                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| `postgres.pass`         | `postgres.pass`         | Postgres user's password                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| `dialect`               | `dialect`               | Can be `mysql`, `postgres `or `bolt`                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| `port`                  | `port`                  | TCP port on which the web interface will be available. Default: 3000                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| `interface`             | `interface`             | Useful if your server has multiple network interfaces                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| `tmp_path`              | —                       | Path to directory where cloned repositories and generated files are stored. Default: /tmp/semaphore                                                                                                                                                                                                                                                                                                                                                                                                                   |
| `access_key_encryption` | `access-key-encryption` | Secret key used for encrypting access keys in database. Read more in [Database encryption reference](https://docs.ansible-semaphore.com/administration-guide/security#database-encryption).                                                                                                                                                                                                                                                                                                                           |
| `web_host`              | `web-host`              | Can be useful if you want to use Semaphore by the subpath, for example: [http://yourdomain.com/semaphore](http://yourdomain.com/semaphore).                                                                                                                                                                                                                                                                                                                                                                           |
| `email_sender`          | `email-sender`          |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| `email_host`            | `email-host`            |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| `email_port`            | `email-port`            |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| `email_secure`          | `email-secure`          |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| `email_username`        | `email-username`        |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| `email_password`        | `email-password`        |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| `email_alert`           | `email-alert`           |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| `telegram_alert`        | `telegram-alert`        |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| `slack_alert`           | `slack-alert`           |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| `ldap_enable`           | `ldap-enable`           |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| `ldap_needtls`          | `ldap-needtls`          |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| `ldap_binddn`           | `ldap-binddn`           |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| `ldap_bindpassword`     | `ldap-bindpassword`     |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| `ldap_server`           | `ldap-server`           |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| `ldap_searchdn`         | `ldap-searchdn`         |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| `ldap_whoami`           | `ldap-whoami`           | Can be used to disable the LDAP WhoAmI-check after authenticating. Can fix [protocol errors](https://github.com/ansible-semaphore/semaphore/issues/1238) for some LDAP providers.                                                                                                                                                                                                                                                                                                                                     |
| `concurrency_mode`      | `concurrency-mode`      | Can be *unset/empty* or `project` or `node`. When set to `project`, tasks will run in parallel if and only if they do not share the same project id, with no regard to the nodes/hosts that are affected. When set to `node`, a task will run in parallel if and only if the hosts affected by tasks already running does not intersect with the hosts that would be affected by the task in question. If `concurrency_mode` is not specified or left empty, no task will start before the previous one has finished. |
| `max_parallel_tasks`    | `max-parallel-tasks`    | Max allowed parallel tasks if `concurrency-mode` is enabled. Can also be set/changed within the Web UI (project settings).                                                                                                                                                                                                                                                                                                                                                                                            |
