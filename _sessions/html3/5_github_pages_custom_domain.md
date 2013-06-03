---
title: Set-up your domain name
---

There are two things you need to do to get your domain name working with your github pages site
1. Tell your domain registrar (e.g 123-reg or godaddy) to point towards github
2. Tell github that your site should be matched with that domain name when the request gets to github 
Github explains this [here](https://help.github.com/articles/setting-up-a-custom-domain-with-pages)

The second bit is easy:
- Open Sublime Text and create a new file 
- Write your domain name on the first line of the new file e.g:

         mydomain.com

- Save that file as `CNAME` (with no extension) in your `first_site` folder
- Add and commit your changes locally, then push to github:

         git add .
         git commit -m "Added CNAME"
         git push

For the first bit you need to log in to your domain registrar and change the DNS settings. You want an *A-record* pointing to `204.232.175.78` (which is github.com). Note that it can take up to a couple of days for DNS changes to propagate.

If you're using 123-reg, your should log in, select your domain from the list, and click "Manage". You should then go to "Manage DNS".

![123-reg DNS Settings](./assets/dns_settings.png)

(The @ dns entry stands for the root or bare domain.)

Your changes won't take effect immediately. You can check by visiting your url (which should end you up at github), or by running

    $ host yourdomain.com

at the command prompt (or `nslookup` on windows).

