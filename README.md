# nano-postfix-dovecot

Easy ansible role for configuring postfix and dovecot with virtual domains. Sparse on resources, yet highly configurable and versitable

## System design

* SMTP: Postfix (virtual domains)
* IMAP: Dovecot

## Usage

Use the provided role `nanomail`

    ---
    
    - name: Install Mailserver
      hosts: mailserver  
      roles:
        - { role: nanomail, hostname : "mailserver", domain : "mydomain.local" }

After installing, you will need to configure your virtual domains by editing `/etc/postfix/virtual-mboxes`

    joe@mydomain.local    mydomain.local/joe/
    papajoe@mydomain.local      mydomain.local/papajoe/
    papa-joe@mydomain.local      mydomain.local/papajoe/

