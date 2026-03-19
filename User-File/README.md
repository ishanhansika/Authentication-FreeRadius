
## Edit User Conf
```
sudo nano /etc/freeradius/users
```
```
#
#bob     Cleartext-Password := "hello"
#       Reply-Message := "Hello, %{User-Name}"
#
user         Cleartext-Password := "userpassword"
####
```

```
sudo systemctl restart freeradius.service
```
