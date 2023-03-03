# nextcloud-nginx
A working nginx configuration for a nextcloud instance

## Why does this exist?

None of the nginx configs I found online seemed to work for my instance, I presume these are outdated or needed slight adjustments which weren't mentioned.
This configuration has been slightly tweaked and resulted in a functional configuration for my system.

## Installation 

### Nextcloud 

Follow the Nextcloud [installation instructions](https://docs.nextcloud.com/server/latest/admin_manual/installation/example_ubuntu.html), following the /var/www/nextcloud root schema

### Config file installation 

Copy the configuration file to your `/etc/nginx/sites-available/` directory by issuing the following command

```console
TODO
```

Now change the `server_name` placeholder to your domain in the following way:

```console
sed -i 's/server_name/https:\/\/your.domain\/subdomain/g' nextcloud.conf
```

You may also choose to manually complete this step using a text editor of your choice if you are not familiar with sed.

Alternatively one may use `vim` commands:

```console
:%s/server_name/https:\/your.domain\/subdomain/g
```

Now create a symlink to the file in your `sites-enabled` directory

```console
ln -s nextcloud.conf ../sites-enabled/nextcloud.conf
``` 

### SSL

Configure SSL using a service of your choice, certbot example:

```console
TODO 
```

### Final Step

The final remaining step would be to restart nginx, for `systemd` this can be achieved by issuing 

```console
systemctl restart nginx
```

`OpenRC`

```console
rc-service nginx restart
```

For other init systems please consult the man page
