## Install Freeradius LDAP module
```
apt-get install freeradius-ldap
```

### Configure LDAP parameters
```
sudo vim /etc/freeradius/mods-available/ldap
```

### Add or Modify the appopriate lines
```
server = 'LDAP_SERVER_FQDN'
identity = 'cn=admin,dc=inst,dc=ac,dc=lk' #bind User
password = 'YOUR_LDAP_PASSWORD'
base_dn = 'ou=people,dc=inst,dc=ac,dc=lk'
edir_autz = yes
```
(You should consider connecting LDAP with STARTTLS enable. Please consult the ldap module for configurations)

### Enable LDAP Module & Restart Freeradius
```
ln -s /etc/freeradius/mods-available/ldap /etc/freeradius/mods-enabled/ldap
```
```
service freeradius restart
```
