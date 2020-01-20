# Why?
I've done some research and found that the cheapest DUC domain for my KiwiSDR is \*.ovh provided by OVH company. [Registration](https://www.ovh.ie/domains/dotovh.xml) of new domain cost approximately €1.99, renewal - €2.99. 


# How to?
1. You need to have your DUC domain, username and password for management. Please check this [instruction](https://docs.ovh.com/ie/en/domains/hosting_dynhost/#step-1-create-a-dynhost-username)   
2. Logging into your server via [SSH](http://kiwisdr.com/quickstart) and move to /root directory `cd /root`
3. Download script `wget https://raw.githubusercontent.com/kovalroma/ovh-domain-dynamic-dns-update/master/ovh-update.sh`
4. Add your HOSTNAME, USERNAME, PASSWORD. `nano ./ovh-update.sh`,  `Ctrl+X`, `Yes`
5.  Make script executive `chmod +x ./ovh-update.sh`
6. Add 15 minutes interval to check your IP and update if necessary `crontab -e` add line ` */15 * * * * /root/ovh-update.sh ` 
7. Go to ***Log*** tab in your KiwiSDR admin panel and check your status.   


# Disclaimer 
I'm not a real programmer I'm just studying. If you can improve anything in this repo, feel free to add a pull request or a comment.
