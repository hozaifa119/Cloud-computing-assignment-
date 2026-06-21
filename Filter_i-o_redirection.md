## Difficult Linux Filter and I/O Redirection Exercises (Questions Only)

### Exercise 1: Firewall Investigation

1. Navigate to the `centos` directory.
# cd centos
2. Find all occurrences of the word "firewall" in `anaconda-ks.cfg`.
 # grep "firewall" anaconda-ks.cfg
3. Perform a case-insensitive search for "firewall".
 # grep -i "firewall" anaconda-ks.cfg
4. Search for "firewall" in every file within the current directory.
 # grep "firewall" *
5. Search recursively for "firewall" in all subdirectories.
 # grep -r "firewall" .
6. Display only the line numbers where "firewall" appears.
 # grep -n "firewall" anaconda-ks.cfg
7. Count the total number of times "firewall" appears in the file.
 # grep -c "firewall" anaconda-ks.cfg
---

### Exercise 2: SELinux Audit

1. Search the entire `/etc` directory for files containing the word `SELINUX`.
 # grep -r "SELINUX" /etc

2. Display only the names of files containing `SELINUX`.
 # grep -rl "SELINUX" /etc

3. Display the line numbers where `SELINUX` appears.
 # grep -rn "SELINUX" /etc

4. Save all findings into a file named `selinux_audit.txt`.
 # grep -rn "SELINUX" /etc > selinux_audit.txt

---

### Exercise 3: Reverse Search Challenge

1. Display all lines in `anaconda-ks.cfg` that do not contain the word "firewall".
 # grep -v "firewall" anaconda-ks.cfg

2. Display all lines that do not contain either "firewall" or "SELINUX".
# grep -v "firewall,SELINUX" anaconda-ks.cfg

3. Save the filtered output into a new file called `clean_config.txt`.
# grep -v "firewall,SELINUX" anaconda-ks.cfg > clean_config.txt

### Exercise 4: File Navigation and Viewing

1. Display the first 25 lines of `anaconda-ks.cfg`.
# head -n 25 anaconda-ks.cfg

2. Display the last 25 lines of `anaconda-ks.cfg`.
# tail -n 25 anaconda-ks.cfg

3. View the entire file page by page.
# less anaconda-ks.cfg

4. Search for the word "network" while viewing the file. 
# first the command   less anaconda-ks.cfg 
Than we right  /network 


5. Count the total number of lines in the file.
le
# wl -l anaconda-ks.cfg


### Exercise 5: Log Monitoring

1. Monitor system logs in real time.
# tail -f /var/log/secure

2. Open another terminal and attempt several failed SSH logins.
# In anther terminal we right 
1-cd Documanty/os/centosvm
2-vagrant ssh
3-ssh root@localhost
4- and right the pasword 3 time wrong

3. Identify all login-related log entries.
#grep "sshd" /var/log/secure

4. Save all login attempts into a file named `login_activity.log`.
# grep "sshd" /var/log/secure > login_activity.log

5. Count the number of failed login attempts.
# grep -c "Failed password" /var/log/secure

### Exercise 6: User Information Analysis

1. Display all user accounts from `/etc/passwd`.
# cat /etc/passwd

2. Extract only the usernames.
# cut -d: -f1 /etc/passwd

3. Extract usernames and their home directories.
# cut -d: -f1,6 /etc/passwd

4. Extract usernames and their default shells.
# cut -d: -f1,7 /etc/passwd

5. Count the total number of users on the system.
# wc -l /etc/passwd


### Exercise 7: AWK Reporting Challenge

1. Create a report showing only usernames.
# awk -F: '{print $1}' /etc/passwd

2. Create a report showing usernames and user IDs.
# awk -F: '{print $1,$3}' /etc/passwd

3. Create a report showing usernames, home directories, and login shells.
# awk -F: '{print $1,$6,$7}' /etc/passwd

4. Save the report into `user_report.txt`.
# awk -F: '{print $1,$6,$7}' /etc/passwd > user_report.txt

### Exercise 8: Search and Replace Challenge

1. Create a file named `virus_report.txt`.
# touch virus_report.txt

2. Add the word "coronavirus" at least 50 times in different lines.
# vim virus_report.txt
and than we can make copy for the word 

3. Replace every occurrence of "coronavirus" with "covid19".
# sed -i 's/coronavirus/covid19/g' virus_report.txt

4. Verify that no occurrence of "coronavirus" remains.
# grep "coronavirus" virus_report.txt

5. Count the number of replacements performed.
# grep -c "covid19" virus_report.txt

### Exercise 9: Advanced SED Exercise

1. Create a text file containing multiple references to "coronavirus".
 # touch virus.txt
vim virus.txt

2. Replace all occurrences with "firstborntechnologies" without modifying the original file.
# sed 's/coronavirus/firstborntechnologies/g' virus.txt

3. Modify the original file permanently.
# sed -i 's/coronavirus/firstborntechnologies/g' virus.txt

4. Replace only the first occurrence on each line.
# sed 's/coronavirus/firstborntechnologies/' virus.txt

5. Replace only occurrences found between lines 10 and 20.
# sed '10,20s/coronavirus/firstborntechnologies/g' virus.txt

### Exercise 10: Recursive Search Challenge

1. Create three directories and multiple files.
# mkdir dir1 dir2 dir3

2. Add the word "database" in some files.
# touch hozaifa1.txt 
# vim hozaifa1.txt
and than add the word "database"

3. Search recursively for the word "database".
# grep -r "database" .

4. Display only filenames containing the word.
# grep -rl "database" .

5. Count how many files contain the word.
# grep -rl "database" . | wc -l


### Exercise 11: Security Investigation

1. Search all files under `/etc` for occurrences of:

   * firewall
   * ssh
   * selinux
2. Display matching lines with line numbers.
3. Save the results into `security_report.txt`.
4. Count the total number of matches for each keyword.

---

### Exercise 12: User Account Forensics

1. Determine whether a user named `hacker` exists.
2. Find the user's UID.
3. Find the user's home directory.
4. Find the user's login shell.
5. Save all findings into `hacker_report.txt`.

---

### Exercise 13: Configuration File Audit

1. Find all configuration files containing the word "network".
2. Display only the matching lines.
3. Display only filenames.
4. Save the filenames into `network_configs.txt`.
5. Count the total number of matching files.

---

### Exercise 14: Log Analysis Challenge

1. Extract all lines containing the word "error" from a log file.
2. Ignore case sensitivity.
3. Save the output into `error_report.txt`.
4. Display only the first 20 errors.
5. Display only the last 20 errors.

---

### Exercise 15: Data Extraction Challenge

1. Extract the first column from `/etc/passwd`.
2. Extract the third column from `/etc/passwd`.
3. Extract the seventh column from `/etc/passwd`.
4. Create a report showing:

   * Username
   * UID
   * Shell

---

### Exercise 16: Expert-Level Challenge

1. Search all files under `/etc` recursively.
2. Find occurrences of:

   * firewall
   * selinux
   * ssh
   * network
3. Ignore case sensitivity.
4. Display line numbers.
5. Save results into `system_audit.txt`.
6. Count the total matches for each keyword.

---

### Exercise 17: DevOps Troubleshooting Scenario

A web application is not accessible.

1. Search logs for the word "failed".
2. Search logs for the word "error".
3. Search logs for the word "connection".
4. Save all findings into `troubleshooting_report.txt`.
5. Display the last 50 entries from the report.

---

### Exercise 18: Interview-Level Challenge

Using only:

* grep
* awk
* cut
* sed
* head
* tail
* cat

Create a report that displays:

```text
USERNAME | UID | HOME DIRECTORY | SHELL
```

and save it into `employee_report.txt`.

---

### Exercise 19: Very Difficult Challenge

Create a file containing:

* usernames
* IP addresses
* timestamps
* login statuses

Extract:

1. Only usernames.
2. Only IP addresses.
3. Only failed logins.
4. Only successful logins.
5. Generate separate reports for each category.

---

### Exercise 20: Master Challenge

Without using any GUI tools:

1. Monitor logs in real time.
2. Detect failed SSH logins.
3. Extract usernames involved.
4. Save findings into `security_incidents.txt`.
5. Count total incidents.
6. Display the five most recent incidents.
7. Generate a final audit report for management.## Difficult Linux Filter and I/O Redirection Exercises (Questions Only)

### Exercise 1: Firewall Investigation

1. Navigate to the `centos` directory.
# cd centos
2. Find all occurrences of the word "firewall" in `anaconda-ks.cfg`.
 # grep "firewall" anaconda-ks.cfg
3. Perform a case-insensitive search for "firewall".
 # grep -i "firewall" anaconda-ks.cfg
4. Search for "firewall" in every file within the current directory.
 # grep "firewall" *
5. Search recursively for "firewall" in all subdirectories.
 # grep -r "firewall" .
6. Display only the line numbers where "firewall" appears.
 # grep -n "firewall" anaconda-ks.cfg
7. Count the total number of times "firewall" appears in the file.
 # grep -c "firewall" anaconda-ks.cfg
---

### Exercise 2: SELinux Audit

1. Search the entire `/etc` directory for files containing the word `SELINUX`.
 # grep -r "SELINUX" /etc

2. Display only the names of files containing `SELINUX`.
 # grep -rl "SELINUX" /etc

3. Display the line numbers where `SELINUX` appears.
 # grep -rn "SELINUX" /etc

4. Save all findings into a file named `selinux_audit.txt`.
 # grep -rn "SELINUX" /etc > selinux_audit.txt

---

### Exercise 3: Reverse Search Challenge

1. Display all lines in `anaconda-ks.cfg` that do not contain the word "firewall".
 # grep -v "firewall" anaconda-ks.cfg

2. Display all lines that do not contain either "firewall" or "SELINUX".
# grep -v "firewall,SELINUX" anaconda-ks.cfg

3. Save the filtered output into a new file called `clean_config.txt`.
# grep -v "firewall,SELINUX" anaconda-ks.cfg > clean_config.txt

### Exercise 4: File Navigation and Viewing

1. Display the first 25 lines of `anaconda-ks.cfg`.
# head -n 25 anaconda-ks.cfg

2. Display the last 25 lines of `anaconda-ks.cfg`.
# tail -n 25 anaconda-ks.cfg

3. View the entire file page by page.
# less anaconda-ks.cfg

4. Search for the word "network" while viewing the file. 
# first the command   less anaconda-ks.cfg 
Than we right  /network 


5. Count the total number of lines in the file.
le
# wl -l anaconda-ks.cfg


### Exercise 5: Log Monitoring

1. Monitor system logs in real time.
# tail -f /var/log/secure

2. Open another terminal and attempt several failed SSH logins.
# In anther terminal we right 
1-cd Documanty/os/centosvm
2-vagrant ssh
3-ssh root@localhost
4- and right the pasword 3 time wrong

3. Identify all login-related log entries.
#grep "sshd" /var/log/secure

4. Save all login attempts into a file named `login_activity.log`.
# grep "sshd" /var/log/secure > login_activity.log

5. Count the number of failed login attempts.
# grep -c "Failed password" /var/log/secure

### Exercise 6: User Information Analysis

1. Display all user accounts from `/etc/passwd`.
# cat /etc/passwd

2. Extract only the usernames.
# cut -d: -f1 /etc/passwd

3. Extract usernames and their home directories.
# cut -d: -f1,6 /etc/passwd

4. Extract usernames and their default shells.
# cut -d: -f1,7 /etc/passwd

5. Count the total number of users on the system.
# wc -l /etc/passwd


### Exercise 7: AWK Reporting Challenge

1. Create a report showing only usernames.
# awk -F: '{print $1}' /etc/passwd

2. Create a report showing usernames and user IDs.
# awk -F: '{print $1,$3}' /etc/passwd

3. Create a report showing usernames, home directories, and login shells.
# awk -F: '{print $1,$6,$7}' /etc/passwd

4. Save the report into `user_report.txt`.
# awk -F: '{print $1,$6,$7}' /etc/passwd > user_report.txt

### Exercise 8: Search and Replace Challenge

1. Create a file named `virus_report.txt`.
# touch virus_report.txt

2. Add the word "coronavirus" at least 50 times in different lines.
# vim virus_report.txt
and than we can make copy for the word 

3. Replace every occurrence of "coronavirus" with "covid19".
# sed -i 's/coronavirus/covid19/g' virus_report.txt

4. Verify that no occurrence of "coronavirus" remains.
# grep "coronavirus" virus_report.txt

5. Count the number of replacements performed.
# grep -c "covid19" virus_report.txt

### Exercise 9: Advanced SED Exercise

1. Create a text file containing multiple references to "coronavirus".
 # touch virus.txt
vim virus.txt

2. Replace all occurrences with "firstborntechnologies" without modifying the original file.
# sed 's/coronavirus/firstborntechnologies/g' virus.txt

3. Modify the original file permanently.
# sed -i 's/coronavirus/firstborntechnologies/g' virus.txt

4. Replace only the first occurrence on each line.
# sed 's/coronavirus/firstborntechnologies/' virus.txt

5. Replace only occurrences found between lines 10 and 20.
# sed '10,20s/coronavirus/firstborntechnologies/g' virus.txt

### Exercise 10: Recursive Search Challenge

1. Create three directories and multiple files.
# mkdir dir1 dir2 dir3

2. Add the word "database" in some files.
# touch hozaifa1.txt 
# vim hozaifa1.txt
and than add the word "database"

3. Search recursively for the word "database".
# grep -r "database" .

4. Display only filenames containing the word.
# grep -rl "database" .

5. Count how many files contain the word.
# grep -rl "database" . | wc -l


### Exercise 11: Security Investigation

1. Search all files under `/etc` for occurrences of:

   * firewall
   * ssh
   * selinux
# grep -r "firewall" /etc
# grep -r "ssh" /etc
# grep -r "selinux" /etc

2. Display matching lines with line numbers.
# grep -rn "firewall" /etc
# grep -rn "ssh" /etc
# grep -rn "selinux" /etc

3. Save the results into `security_report.txt`.
# grep -rn "firewall" /etc > security_report.txt
# grep -rn "ssh" /etc >> security_report.txt
# grep -rn "selinux" /etc >> security_report.txt

4. Count the total number of matches for each keyword.
# grep -r "firewall" /etc | wc -l
# grep -r "ssh" /etc | wc -l
# grep -r "selinux" /etc | wc -l

### Exercise 12: User Account Forensics

1. Determine whether a user named `hacker` exists.
# grep "hacker" /etc/passwd

2. Find the user's UID.
# grep "hacker" /etc/passwd | cut -d: -f3

3. Find the user's home directory.
# grep "hacker" /etc/passwd | cut -d: -f6

4. Find the user's login shell.
# grep "hacker" /etc/passwd | cut -d: -f7

5. Save all findings into `hacker_report.txt`.
# grep "hacker" /etc/passwd > hacker_report.txt


### Exercise 13: Configuration File Audit

1. Find all configuration files containing the word "network".
# grep -rl "network" /etc

2. Display only the matching lines.
# grep -r "network" /etc

3. Display only filenames.
# grep -rl "network" /etc

4. Save the filenames into `network_configs.txt`.
# grep -rl "network" /etc > network_configs.txt

5. Count the total number of matching files.
# grep -rl "network" /etc | wc -l

### Exercise 14: Log Analysis Challenge

1. Extract all lines containing the word "error" from a log file.
# grep "error" system.log

2. Ignore case sensitivity.
# grep -i "error" system.log

3. Save the output into `error_report.txt`.
# grep -i "error" system.log > error_report.txt

4. Display only the first 20 errors.
# grep -i "error" system.log | head -20

5. Display only the last 20 errors.
# grep -i "error" system.log | tail -20


### Exercise 15: Data Extraction Challenge

1. Extract the first column from `/etc/passwd`.
# cut -d: -f1 /etc/passwd

2. Extract the third column from `/etc/passwd`.
# cut -d: -f3 /etc/passwd

3. Extract the seventh column from `/etc/passwd`.
# cut -d: -f7 /etc/passwd

4. Create a report showing:

   * Username
   * UID
   * Shell
# awk -F: '{print $1,$3,$7}' /etc/passwd

### Exercise 16: Expert-Level Challenge

1. Search all files under `/etc` recursively.
# grep -r "firewall" /etc
2. Find occurrences of:

   * firewall
   * selinux
   * ssh
   * network
# grep -r "firewall" /etc
# grep -r "selinux" /etc
# grep -r "ssh" /etc
# grep -r "network" /etc


3. Ignore case sensitivity.
# grep -ri "selinux" /etc
# grep -ri "selinux" /etc
# grep -ri "ssh" /etc
# grep -ri "network" /etc

4. Display line numbers.
# grep -rin "firewall" /etc
# grep -rin "selinux" /etc
# grep -rin "selinux" /etc
# grep -rin "ssh" /etc
# # grep -rin "network" /etc

5. Save results into `system_audit.txt`.
# grep -rin "firewall" /etc > system_audit.txt
# grep -rin "selinux" /etc >> system_audit.txt
# grep -rin "ssh" /etc >> system_audit.txt
# # grep -rin "network" /etc >> system_audit.txt

6. Count the total matches for each keyword.
# grep -ri "firewall" /etc | wc -l
#grep -ri "selinux" /etc | wc -l
# grep -ri "ssh" /etc | wc -l
# grep -ri "network" /etc | wc -l

### Exercise 17: DevOps Troubleshooting Scenario

A web application is not accessible.

1. Search logs for the word "failed".
# grep -i "failed" /var/log/messages

2. Search logs for the word "error".
# grep -i "error" /var/log/messages

3. Search logs for the word "connection".
# grep -i "connection" /var/log/messages

4. Save all findings into `troubleshooting_report.txt`# grep -i "failed" /var/log/messages > troubleshooting_report.txt
# grep -i "error" /var/log/messages > troubleshooting_report.txt
# grep -i "connection" /var/log/messages > troubleshooting_report.txt

5. Display the last 50 entries from the report.
# tail -50 troubleshooting_report.txt

### Exercise 18: Interview-Level Challenge

Using only:

* grep
* awk
* cut
* sed
* head
* tail
* cat

Create a report that displays:

```text
USERNAME | UID | HOME DIRECTORY | SHELL
```

and save it into `employee_report.txt`.

# awk -F: '{print $1,"|",$3,"|",$6,"|",$7}' /etc/passwd > employee_report.txt

and than we can do cat to see 
# cat employee_report.txt


### Exercise 19: Very Difficult Challenge

Create a file containing:

* usernames
* IP addresses
* timestamps
* login statuses
# touch login_data.txt
vim login_data.txt


Extract:

1. Only usernames.
# cut -d: -f1 login_data.txt

2. Only IP addresses. 
# cut -d: -f2 login_data.txt

3. Only failed logins.
# grep "failes" login_data.txt

4. Only successful logins.
# grep "success" login_data.txt

5. Generate separate reports for each category.
# cut -d: -f1 login_data.txt > username.txt
# cut -d: -f1 login_data.txt > username.txt
# cut -d: -f2 login_data.txt > ip_addresses.txt
# grep "failed" login_data.txt > failed_logins.txt
# grep "success" login_data.txt > successful_logins.txt


### Exercise 20: Master Challenge

Without using any GUI tools:

1. Monitor logs in real time.
# tail -f /var/log/secure

2. Detect failed SSH logins.
# In anther terminal we do the command 
# ssh root@localhost
and enter the password incorrectly three times

3. Extract usernames involved.
# grep "Failed password" /var/log/secure

4. Save findings into `security_incidents.txt`.
# grep "Failed password" /var/log/secure > security_incidents.txt

5. Count total incidents.
# grep -c "Failed password" /var/log/secure

6. Display the five most recent incidents.
# tail -5 security_incidents.txt

7. Generate a final audit report for management.
# echo "Security Audit Report" > final_audit.txt
# grep "Failed password" /var/log/secure >> final_audit.txt
