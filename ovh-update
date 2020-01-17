#!/bin/bash

HOSTNAME="put_your_hostname"
USERNAME="put_your_username"
PASSWORD="put_your_password"

PUBLIC_IP=$(curl -s -k https://domains.google.com/checkip)
DDNS_IP=$(dig +short ${HOSTNAME})

if [ "$PUBLIC_IP" != "$DDNS_IP" ]; then
URL="https://www.ovh.com/nic/update?system=dyndns&hostname=${HOSTNAME}&myip=${PUBLIC_IP}"

curl -s -k --user "${USERNAME}:${PASSWORD}" "$URL" 

else
echo 'No changes needed'

fi

exit 0
