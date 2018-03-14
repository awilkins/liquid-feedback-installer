# Liquid Feedback Installation

This ansible script should work fine on a Debian box (I used Squeeze).

Vagrantfile provided should you just want to do

`vagrant up`

## Creating Admin User

Much of the documentation for LiquidFeedback is out of date!

In particular, to create empty admin account you need to set `activated` and `last_activity`
or the table violates a view constraint.

```sql
INSERT INTO member (login, name, admin, password, activated, last_activity) VALUES ('admin', 'Administrator', TRUE, '$1$/EMPTY/$NEWt7XJg2efKwPm4vectc1', now(), now());
```

I also haven't added the rows suggested in the [install guide](http://www.public-software-group.org/mercurial/liquid_feedback_frontend/raw-file/tip/INSTALL.html)
