# Ansible role Nginx

Version: 0.1.1

Supported OS: Ubuntu

This role enables you to install Nginx. It has support for Let's Encrypt or self-signed certificates.

- Configures Monit for monitoring
- Configures firewall using UFW: opens HTTP port and when required the port for HTTPS

## Role variables

```
nginx_ssl_hostname: example.com   # Hostname to request SSL certificate for
nginx_ssl_folder: /etc/nginx/ssl  # Folder to install the certificate

# Set True to install Let's Encrypt certificate.
nginx_use_letsencrypt: False                      
# Mail address for requesting a Let's Encrypt certificate.
nginx_letsencrypt_email: admin@example.com        
# Web-root where Let's Encrypt prepares it's challenge.
nginx_letsencrypt_webroot: /usr/share/nginx/html  

# Set True to install self-signed certificate.
nginx_use_self_signed_ssl: False  
```

## example

```
- hosts: all
  roles:
    - role: nginx
      nginx_letsencrypt_email: joe@example.com
      nginx_ssl_hostname: example.com
      nginx_use_letsencrypt: True
```
