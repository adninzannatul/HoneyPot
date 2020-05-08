# HoneyPot
1.The MHN Admin VM is provisioned with the following attributes:

   - Ubuntu 18.04 Minimal
   - HTTP traffic allowed (port 80)
   - TCP ports 3000 and 10000 need to be open to allow incoming (aka 'ingress') traffic for geolocation and honeypot sensor data.
   Commands that are run-
   gcloud compute firewall-rules list

gcloud compute firewall-rules create http \
    --allow tcp:80 \
    --description="Allow HTTP from Anywhere" \
    --direction ingress \
    --target-tags="mhn-admin"

gcloud compute firewall-rules create honeymap \
    --allow tcp:3000 \
    --description="Allow HoneyMap Feature from Anywhere" \
    --direction ingress \
    --target-tags="mhn-admin"

gcloud compute firewall-rules create hpfeeds \
    --allow tcp:10000 \
    --description="Allow HPFeeds from Anywhere" \
    --direction ingress \
    --target-tags="mhn-admin"

         
 ![alt-text]()
