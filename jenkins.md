Script for finding out which job is eating your disk space
----------------------------------------------------------

```
println "df -h".execute().text
def p = "du -h -d 1 /var/lib/jenkins/jobs".execute() | "sort -rh".execute()
p.waitFor()
println p.text
```
