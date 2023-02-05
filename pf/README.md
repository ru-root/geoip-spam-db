
```
table <DENY_UNKNOWN> const file "/etc/pf/spam_unknown_db.conf"
table <DENY_SPAM>    const file "/etc/pf/spam_db.conf"


pass in quick on the0 proto tcp from ! <DENY_UNKNOWN> port { 465 587 25 } label "SMTP"
pass in quick on the0 proto tcp from ! <DENY_UNKNOWN> port = 3389 label "IMAP"
pass in quick on the0 proto tcp from ! <DENY_UNKNOWN> port = 3389 label "RDP"

```
