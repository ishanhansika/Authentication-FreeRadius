
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

<img width="886" height="60" alt="image" src="https://github.com/user-attachments/assets/d3289daa-8136-49a9-a087-57cfeae69a48" />

