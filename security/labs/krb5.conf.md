[libdefaults]
default_realm = HADOOP.COM
dns_lookup_kdc = false
dns_lookup_realm = false
ticket_lifetime = 86400
renew_lifetime = 604800
forwardable = true
default_tgs_enctypes = aes256-cts
default_tkt_enctypes = aes256-cts
permitted_enctypes = aes256-cts
udp_preference_limit = 1
kdc_timeout = 3000
[realms]
HADOOP.COM = {
kdc = grcsebcm
admin_server = grcsebcm
default_domain = hadoop.com
}
[domain_realm]
hadoop.com = HADOOP.COM
.hadoop.com = HADOOP.COM
