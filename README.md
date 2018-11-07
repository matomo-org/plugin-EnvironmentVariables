# Matomo EnvironmentVariables Plugin

## Description

Override any Matomo config with environment variables. To overwrite any setting simply specify an environment variable in the following format:

```
MATOMO_$CATEGORY_$SETTING
```

For example to overwrite the database username and password which is usually defined in the `config/config.ini.php` like this:

```ini
[database]
username = "root"
password = "secure"
```

using environment variables like this:

```bash
export MATOMO_DATABASE_USERNAME=root
export MATOMO_DATABASE_PASSWORD=secure
```

### Known issues:
* Configuration arrays are currently not supported, for example you cannot define which `Plugins[]` should be loaded.
* At some point your Matomo may save/write the config file, for example when changing certain settings through the UI such as the trusted hosts. In this case, the currently read environment variables will be saved in the config file.

