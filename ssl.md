apt install -y socat
curl https://get.acme.sh | sh
source ~/.bashrc
acme.sh --upgrade --auto-upgrade
acme.sh --set-default-ca --server letsencrypt

acme.sh --issue -d domain.com --standalone --keylength ec-256

acme.sh --install-cert -d domain.com --ecc \
--fullchain-file /etc/ssl/private/fullchain.cer \
--key-file /etc/ssl/private/private.key

chown -R nobody:nogroup /etc/ssl/private
