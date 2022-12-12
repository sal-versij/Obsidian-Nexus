# WAPT
Tre varianti:
- Black box
- White box
- Gray Box

## Tools
`fping <ip>\<mask>`: ping all devices in a network
`nmap`: Port scanning
`sqlmap`: Sql Injection Penetration Testing
`gobuster`: directory discoverer

## Trace
1. Sqlinjection in login
2. directory discovery with gobuster
3. settings.php has a file upload for images, possible entrypoint for a reverse shell
4. php reverse shell found online
5. connect to the reverse shell with netcat
6. whe are a daemon user, trying to scale privilages
7. `find / -perm -4000 -type f -exec ls -al {} \; 2>/dev/null` per trovare il bit su id di un'altro user
8. lateral movement
9. search around
10. `cat /etc/crontab` to see what scripts this user executes
11. write in an executed script by that user a reverse