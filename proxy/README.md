# Proxy for OpenClaw

- **Prerequisite: nginx**
- To be run in an admin user space.
- The proxy is restricted to local machine access only, and accepts plain HTTP requests.

## Install Nginx

```shell
brew install nginx
```

## Set the Keys

Simply update [secrets.conf](./secrets.conf) with your Anthropic and Brave keys.\
_Only those were relevant for me, feel free to contribute others too_ 🙂

> Nginx does not natively support the use of environment variables within most configuration blocks. Therefore, the simplest and secure way to manage secret keys is by storing them in a file located in the admin user's space, which is inaccessible to unauthorized users.

## Testing the Configs

Run the following command to validate if the configurations are fine.
```shell
nginx -c "$PWD/nginx.conf" -t
```

> `nginx.conf` loads `mime.types` from the path `/opt/homebrew/etc/nginx/` (Apple Silicon). In case the path is different in your system and the test failed, please correct the same in `nginx.conf`.

## Start Nginx

```shell
nginx -c "$PWD/nginx.conf"
```

> Nginx is intentionally started in the foreground to enhance observability. I prefer to keep it running in an open terminal session within the admin user account.

## Test

### Anthropic

```shell
curl http://localhost:8080/anthropic/v1/chat/completions \
  -H "Content-Type: application/json" \
  -H "Authorization: Bearer dummy" \
  -d '{
    "model": "claude-haiku-4-5",
    "messages": [
      {"role": "user", "content": "Hi"}
    ]
  }'
```

### Brave

```shell
curl "http://localhost:8080/brave/res/v1/web/search?q=OpenClaw" \
  -H "Accept: application/json"
```
