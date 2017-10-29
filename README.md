# soriyath/debian-dotnetcore2
> A Dockerfile for a .netcore2 stack running on swiss-fr localized debian stretch stack 

## Supervisord
The stack runs with supervisord.

### Configuration
> See [Supervisor's configuration documentation](http://supervisord.org/configuration.html#program-x-section-settings)

1. Create your own container that inherits this one, and add a `webapp.sv.conf` describing your service.
2. Add this directive to your Dockerfile: 
`ADD <file_name>.sv.conf /etc/supervisor/conf.d/<file_name>.sv.conf`

3. To kick-start the different services, add this line to your Dockerfile:
`CMD ["supervisord", "-c", "/etc/supervisor/supervisor.conf"]`
