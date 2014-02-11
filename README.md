whois.geek.nz
=============

a whois service that is current

```
cat >> .bashrc <<EOF
resolver=".whois.geek.nz"
iwhois() {
    domain=$1
    tld=`echo $domain | awk -F "." '{print $NF}'`
    whois -h $tld$resolver "$@" ;
}
