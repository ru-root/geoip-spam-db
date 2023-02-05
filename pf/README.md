
- Example: **pf_rule.conf**
```
#### DENY
table <DENY_UNKNOWN> const file "/etc/pf/spam_unknown_db.conf"
table <DENY_SPAM>    const file "/etc/pf/spam_db.conf"


block drop in quick on the0 inet proto tcp from <DENY_UNKNOWN> label "UNKNOWN"

pass in quick on the0 inet proto tcp from ! <DENY_SPAM> port { 465 587 25 } label "SMTP"
pass in quick on the0 inet proto tcp from ! <DENY_SPAM> port = 3389         label "IMAP"
pass in quick on the0 inet proto tcp from ! <DENY_SPAM> port = 3389         label "RDP"

...

```
