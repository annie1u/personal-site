---
layout: post
category: note
---
#### Domain 
I had a friend who enjoyed [Porkbun](porkbun.com) based in PNW, so I was interested in trying their domain service out. Finding a domain name: annielu.dev was easy enough. I followed [Github Page's custom domain documentation](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site) with the CName file & DNS Provider configurations. Luckily, Porkbun offers Github Pages support, so I didn't have to manually enter in the records and it could generate the records for me. 

#### SSL Cert 
Porkbun also offers [free SSL Certificates with Let's Encrypt](https://porkbun.com/products/ssl). Github Pages is able to detect this and lets me [enforce HTTPS in settings](https://docs.github.com/en/pages/getting-started-with-github-pages/securing-your-github-pages-site-with-https). If Porkbun had not offered SSL Certificates, I would've used [certbot](https://certbot.eff.org/) to get a certificate and need to manually set-up and/or update each time the certificate expires. 

#### Static Website
Setting up a static website sounded simple enough. Unfortunately, Jekyll is written in Ruby and I own a macbook -- a terrible curse indeed. While trying to install Ruby on my mac, I ran into tons of configuration errors. I searched the forums for answers, looking for the fix, but I wasn't able to escape dependency hellscape. In the end, I  decided to run a Docker Image of Ruby, following this [Github Guide](https://github.com/BillRaymond/my-jekyll-docker-website) and this [Docker wiki](https://docs.docker.com/get-started/docker-concepts/the-basics/what-is-an-image/) I found. I setup gems that were the same version as Github Pages, but if I were to try this again, I'd use the official [Github Pages Ruby gem](https://github.com/github/pages-gem ) that I later found. 

After properly installing Ruby, Jekyll, and other stuff, I used the remote theme: [No-Style-Please](https://github.com/riggraz/no-style-please) for it's fast performance and minimalist appeal. Eventually, I decided that I wanted to be able to customize the theme in the future, so I installed it with guidance from [Jekyll's theme documentation](https://jekyllrb.com/docs/themes/#converting-gem-based-themes-to-regular-themes). The rest was adding content & tweaking the menu.yml and _config.yml files. 