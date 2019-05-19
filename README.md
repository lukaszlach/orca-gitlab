# lukaszlach / orca-gitlab

https://github.com/lukaszlach/orca

## Using [Play with Docker](labs.play-with-docker.com)

1. Change `.env` file to contain fqdn. To do so copy hostname from ssh command and replace `@` with `.`
2. After running `docker-compose up -d gitlab` you need to change limit for max domain name to do so in 'gitlab/config/gitlab.rb' uncomment  and change `server_names_hash_bucket_size` to 128 characters taken from 
[docs](https://docs.gitlab.com/omnibus/common_installation_problems/#nginx-error-could-not-build-server_names_hash-you-should-increase-server_names_hash_bucket_size)

    ```
    nginx['server_names_hash_bucket_size'] = 128
    ```

3. Restart gitlab `docker-compose restart gitlab`
