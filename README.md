# globomap-driver-acs
Python library for globomap-loader to get data from Cloudstack

## Plugin environment variables configuration
All of the environment variables below must be set for the plugin to work properly.
The variables are the combination of the the prefix 'ACS', the environment (region) 
code passed on the driver constructor and the variable name.

| Variable                    |  Description                    | Example                                      |
|-----------------------------|---------------------------------|----------------------------------------------|
| ACS_$env_API_URL            | Cloudstack API URL              | http://yourdomain.cloudstack:8080/api/client |
| ACS_$env_API_KEY            | Cloudstack API key              | jIkLGAz0yqbJC15lS_XqHKRPZXI8M6               |
| ACS_$env_API_SECRET_KEY     | Cloudstack API Secret           | RJK0Xhb3iMwrIUIxJ3T7jL5fFrG14b               |
| ACS_$env_RMQ_HOST           | Cloudstack RabbitMQ host        | rabbitmq.yourdomain.cloudstack               |
| ACS_$env_RMQ_USER           | Cloudstack RabbitMQ user        | user-name                                    |
| ACS_$env_RMQ_PASSWORD       | Cloudstack RabbitMQ password    | password                                     |
| ACS_$env_RMQ_PORT           | Cloudstack RabbitMQ port        | 5673 (default value)                         |
| ACS_$env_RMQ_QUEUE          | Cloudstack RabbitMQ queue name  | events                                       |
| ACS_$env_RMQ_LOADER_EXCHANGE| Cloudstack RabbitMQ Exchange    | cloudstack-globomap-loader                   |
| ACS_$env_RMQ_VIRTUAL_HOST   | Cloudstack RabbitMQ virtual host| /globomap                                    |
| ACS_$env_PROJECT_ALLOCATION_FILE| Path to the project allocation CSV file| /path/to/file                     |


## Example of use

```python
from globomap_driver_acs.driver import Cloudstack
driver = Cloudstack(env="ENV_NAME")
driver.updates()
```