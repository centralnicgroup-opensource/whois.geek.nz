whois.geek.nz
=============

A whois service that is current.

whois.geek.nz aliases the official whois server for each tld.

While you can use them directly via:

    whois -h ${TLD}.whois.geek.nz

you can make this easier by adding this to your .bashrc or other compatible
shell initialization script:

```
cat >> ~/.bashrc <<EOF

iwhois() {
    resolver=".whois.geek.nz"
    tld=`echo ${@: -1} | awk -F "." '{print $NF}'`
    whois -h $tld$resolver "$@" ;
}
EOF
```

Then you can use `iwhois` as a command that automatically looks at the correct
server.

if you fancy you can even replace the standard `whois` with `iwhois` by adding this:

    alias whois='iwhois'

to the end of your `.profile` or `.bashrc`.

Please submit pull requests/issues if this function doesn't work, or there are
better solutions, for your shell and we can add them.
