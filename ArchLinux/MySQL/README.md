[⬅ Back](../)

# Install MySQL on Arch Linux

Update the system:
```
sudo pacman -Syu
```

Install MySQL:
```
sudo pacman -S mysql
```

Initialize MySQL:
```
sudo mysqld --initialize --user=mysql --basedir=/usr --datadir=/var/lib/mysql
```

Enable and start the MySQL Service:
```
sudo systemctl enable mysqld
sudo systemctl start mysqld
```

Check the password generated: A temporary password is generated for root@localhost: XXXXXX

Configure MySQL, use the password generated:
```
sudo mysql_secure_installation
```


Finally, test the database with the new password:
```
mysql -u root -p
```

