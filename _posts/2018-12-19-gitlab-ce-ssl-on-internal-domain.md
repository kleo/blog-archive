---
layout: post
title: "GitLab-CE SSL on Internal Domain"
category: sysadmin
---

Setting up GitLab-CE with SSL on a Docker container for a internal domain. 

For this setup I used pfSense's Certificate Manager. Created a Certificate Authority and Server Certificates.

My GitLab-CE Docker container is configured to use a physical/macvlan networking interface or dedicated IP on LAN. 

For DNS I am using Unbound/DNS Resolver on pfSense to point the domain to my internal IP address.

Have the GitLab-CE container up and running then ssh into it `docker exec -it gitlab /bin/bash`

Using your favorite editor modify `/etc/gitlab/gitlab.rb`


	external_url 'https://git.example.com'

	postgresql['ssl_ca_file'] = '/etc/gitlab/trusted-certs/git.example.com.pem'

	nginx['redirect_http_to_https'] = true
	nginx['redirect_http_to_https_port'] = 80

	nginx['ssl_certificate'] = "/etc/gitlab/ssl/git.example.com.crt"
	nginx['ssl_certificate_key'] = "/etc/gitlab/ssl/git.example.com.key"


Copy the certificate and key to the directories provided above. 

For the `postgresql['ssl_ca_file']` use the `git.example.com.crt` rename it to `git.example.com.pem`.

Run `gitlab-ctl reconfigure`

Include the CA on your browsers and make sure to trust the CA.
