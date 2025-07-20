---
tags:
  - dev
  - bash
created_at: 2025-07-18 07:14
aliases:
---
## Problem
bash script when running `./mvnw spring-boot:run` in order to run Spring Boot application on the command line
error is `wget: Failed to fetch https://repo.maven.apache.org/maven2/org/apache/maven/apache-maven/3.9.10/apache-maven-3.9.10-bin.zip`

## Solution
- `bash -x <script>`
- this allowed me to see what the script has currently executed
```
$ bash -x mvnw
+ set -euf
+ '[' '' '!=' debug ']'
+ case "$(uname)" in
++ uname
+ '[' '' '!=' true ']'
mvnw: line 114: mvnw/.mvn/wrapper/maven-wrapper.properties: Not a directory

~/java-man/mycoolerapp
$ bash -x ./mvnw
+ set -euf
+ '[' '' '!=' debug ']'
+ case "$(uname)" in
++ uname
+ '[' '' '!=' true ']'
+ IFS==
+ read -r key value
+ case "${key-}" in
+ IFS==
+ read -r key value
+ case "${key-}" in
+ IFS==
+ read -r key value
+ case "${key-}" in
+ IFS==
+ read -r key value
+ case "${key-}" in
+ IFS==
+ read -r key value
+ case "${key-}" in
+ IFS==
+ read -r key value
+ case "${key-}" in
+ IFS==
+ read -r key value
+ case "${key-}" in
+ IFS==
+ read -r key value
+ case "${key-}" in
+ IFS==
+ read -r key value
+ case "${key-}" in
+ IFS==
+ read -r key value
+ case "${key-}" in
+ IFS==
+ read -r key value
+ case "${key-}" in
+ IFS==
+ read -r key value
+ case "${key-}" in
+ IFS==
+ read -r key value
+ case "${key-}" in
+ IFS==
+ read -r key value
+ case "${key-}" in
+ IFS==
+ read -r key value
+ case "${key-}" in
+ IFS==
+ read -r key value
+ case "${key-}" in
+ IFS==
+ read -r key value
+ case "${key-}" in
+ IFS==
+ read -r key value
+ case "${key-}" in
+ IFS==
+ read -r key value
+ case "${key-}" in
++ trim https://repo.maven.apache.org/maven2/org/apache/maven/apache-maven/3.9.10/apache-maven-3.9.10-bin.zip
++ printf %s https://repo.maven.apache.org/maven2/org/apache/maven/apache-maven/3.9.10/apache-maven-3.9.10-bin.zip
++ tr -d '[:space:]'
+ distributionUrl=https://repo.maven.apache.org/maven2/org/apache/maven/apache-maven/3.9.10/apache-maven-3.9.10-bin.zip
+ IFS==
+ read -r key value
+ '[' -n https://repo.maven.apache.org/maven2/org/apache/maven/apache-maven/3.9.10/apache-maven-3.9.10-bin.zip ']'
+ case "${distributionUrl##*/}" in
+ MVN_CMD=mvn
+ _MVNW_REPO_PATTERN=/org/apache/maven/
+ '[' -z '' ']'
+ distributionUrlName=apache-maven-3.9.10-bin.zip
+ distributionUrlNameMain=apache-maven-3.9.10-bin
+ distributionUrlNameMain=apache-maven-3.9.10
+ MAVEN_USER_HOME=/home/skrambol/.m2
++ hash_string https://repo.maven.apache.org/maven2/org/apache/maven/apache-maven/3.9.10/apache-maven-3.9.10-bin.zip
++ str=https://repo.maven.apache.org/maven2/org/apache/maven/apache-maven/3.9.10/apache-maven-3.9.10-bin.zip
++ h=0
++ '[' -n https://repo.maven.apache.org/maven2/org/apache/maven/apache-maven/3.9.10/apache-maven-3.9.10-bin.zip ']'
++ char=h
+++ LC_CTYPE=C
+++ printf %d ''\''h'
++ h=104
++ str=ttps://repo.maven.apache.org/maven2/org/apache/maven/apache-maven/3.9.10/apache-maven-3.9.10-bin.zip
++ '[' -n ttps://repo.maven.apache.org/maven2/org/apache/maven/apache-maven/3.9.10/apache-maven-3.9.10-bin.zip ']'
++ char=t
+++ LC_CTYPE=C
+++ printf %d ''\''t'
++ h=3340
++ str=tps://repo.maven.apache.org/maven2/org/apache/maven/apache-maven/3.9.10/apache-maven-3.9.10-bin.zip
++ '[' -n tps://repo.maven.apache.org/maven2/org/apache/maven/apache-maven/3.9.10/apache-maven-3.9.10-bin.zip ']'
++ char=t
+++ LC_CTYPE=C
+++ printf %d ''\''t'
++ h=103656
++ str=ps://repo.maven.apache.org/maven2/org/apache/maven/apache-maven/3.9.10/apache-maven-3.9.10-bin.zip
++ '[' -n ps://repo.maven.apache.org/maven2/org/apache/maven/apache-maven/3.9.10/apache-maven-3.9.10-bin.zip ']'
++ char=p
+++ LC_CTYPE=C
+++ printf %d ''\''p'
++ h=3213448
++ str=s://repo.maven.apache.org/maven2/org/apache/maven/apache-maven/3.9.10/apache-maven-3.9.10-bin.zip
++ '[' -n s://repo.maven.apache.org/maven2/org/apache/maven/apache-maven/3.9.10/apache-maven-3.9.10-bin.zip ']'
++ char=s
+++ LC_CTYPE=C
+++ printf %d ''\''s'
++ h=99617003
++ str=://repo.maven.apache.org/maven2/org/apache/maven/apache-maven/3.9.10/apache-maven-3.9.10-bin.zip
++ '[' -n ://repo.maven.apache.org/maven2/org/apache/maven/apache-maven/3.9.10/apache-maven-3.9.10-bin.zip ']'
++ char=:
+++ LC_CTYPE=C
+++ printf %d ''\'':'
++ h=3088127151
++ str=//repo.maven.apache.org/maven2/org/apache/maven/apache-maven/3.9.10/apache-maven-3.9.10-bin.zip
++ '[' -n //repo.maven.apache.org/maven2/org/apache/maven/apache-maven/3.9.10/apache-maven-3.9.10-bin.zip ']'
++ char=/
+++ LC_CTYPE=C
+++ printf %d ''\''/'
++ h=1242661216
++ str=/repo.maven.apache.org/maven2/org/apache/maven/apache-maven/3.9.10/apache-maven-3.9.10-bin.zip
++ '[' -n /repo.maven.apache.org/maven2/org/apache/maven/apache-maven/3.9.10/apache-maven-3.9.10-bin.zip ']'
++ char=/
+++ LC_CTYPE=C
+++ printf %d ''\''/'
++ h=4162759375
++ str=repo.maven.apache.org/maven2/org/apache/maven/apache-maven/3.9.10/apache-maven-3.9.10-bin.zip
++ '[' -n repo.maven.apache.org/maven2/org/apache/maven/apache-maven/3.9.10/apache-maven-3.9.10-bin.zip ']'
++ char=r
+++ LC_CTYPE=C
+++ printf %d ''\''r'
++ h=196521859
++ str=epo.maven.apache.org/maven2/org/apache/maven/apache-maven/3.9.10/apache-maven-3.9.10-bin.zip
++ '[' -n epo.maven.apache.org/maven2/org/apache/maven/apache-maven/3.9.10/apache-maven-3.9.10-bin.zip ']'
++ char=e
+++ LC_CTYPE=C
+++ printf %d ''\''e'
++ h=1797210434
++ str=po.maven.apache.org/maven2/org/apache/maven/apache-maven/3.9.10/apache-maven-3.9.10-bin.zip
++ '[' -n po.maven.apache.org/maven2/org/apache/maven/apache-maven/3.9.10/apache-maven-3.9.10-bin.zip ']'
++ char=p
+++ LC_CTYPE=C
+++ printf %d ''\''p'
++ h=4173916014
++ str=o.maven.apache.org/maven2/org/apache/maven/apache-maven/3.9.10/apache-maven-3.9.10-bin.zip
++ '[' -n o.maven.apache.org/maven2/org/apache/maven/apache-maven/3.9.10/apache-maven-3.9.10-bin.zip ']'
++ char=o
+++ LC_CTYPE=C
+++ printf %d ''\''o'
++ h=542377665
++ str=.maven.apache.org/maven2/org/apache/maven/apache-maven/3.9.10/apache-maven-3.9.10-bin.zip
++ '[' -n .maven.apache.org/maven2/org/apache/maven/apache-maven/3.9.10/apache-maven-3.9.10-bin.zip ']'
++ char=.
+++ LC_CTYPE=C
+++ printf %d ''\''.'
++ h=3928805773
++ str=maven.apache.org/maven2/org/apache/maven/apache-maven/3.9.10/apache-maven-3.9.10-bin.zip
++ '[' -n maven.apache.org/maven2/org/apache/maven/apache-maven/3.9.10/apache-maven-3.9.10-bin.zip ']'
++ char=m
+++ LC_CTYPE=C
+++ printf %d ''\''m'
++ h=1533894784
++ str=aven.apache.org/maven2/org/apache/maven/apache-maven/3.9.10/apache-maven-3.9.10-bin.zip
++ '[' -n aven.apache.org/maven2/org/apache/maven/apache-maven/3.9.10/apache-maven-3.9.10-bin.zip ']'
++ char=a
+++ LC_CTYPE=C
+++ printf %d ''\''a'
++ h=306098145
++ str=ven.apache.org/maven2/org/apache/maven/apache-maven/3.9.10/apache-maven-3.9.10-bin.zip
++ '[' -n ven.apache.org/maven2/org/apache/maven/apache-maven/3.9.10/apache-maven-3.9.10-bin.zip ']'
++ char=v
+++ LC_CTYPE=C
+++ printf %d ''\''v'
++ h=899108021
++ str=en.apache.org/maven2/org/apache/maven/apache-maven/3.9.10/apache-maven-3.9.10-bin.zip
++ '[' -n en.apache.org/maven2/org/apache/maven/apache-maven/3.9.10/apache-maven-3.9.10-bin.zip ']'
++ char=e
+++ LC_CTYPE=C
+++ printf %d ''\''e'
++ h=2102544976
++ str=n.apache.org/maven2/org/apache/maven/apache-maven/3.9.10/apache-maven-3.9.10-bin.zip
++ '[' -n n.apache.org/maven2/org/apache/maven/apache-maven/3.9.10/apache-maven-3.9.10-bin.zip ']'
++ char=n
+++ LC_CTYPE=C
+++ printf %d ''\''n'
++ h=754384926
++ str=.apache.org/maven2/org/apache/maven/apache-maven/3.9.10/apache-maven-3.9.10-bin.zip
++ '[' -n .apache.org/maven2/org/apache/maven/apache-maven/3.9.10/apache-maven-3.9.10-bin.zip ']'
++ char=.
+++ LC_CTYPE=C
+++ printf %d ''\''.'
++ h=1911096272
++ str=apache.org/maven2/org/apache/maven/apache-maven/3.9.10/apache-maven-3.9.10-bin.zip
++ '[' -n apache.org/maven2/org/apache/maven/apache-maven/3.9.10/apache-maven-3.9.10-bin.zip ']'
++ char=a
+++ LC_CTYPE=C
+++ printf %d ''\''a'
++ h=3409409681
++ str=pache.org/maven2/org/apache/maven/apache-maven/3.9.10/apache-maven-3.9.10-bin.zip
++ '[' -n pache.org/maven2/org/apache/maven/apache-maven/3.9.10/apache-maven-3.9.10-bin.zip ']'
++ char=p
+++ LC_CTYPE=C
+++ printf %d ''\''p'
++ h=2612485119
++ str=ache.org/maven2/org/apache/maven/apache-maven/3.9.10/apache-maven-3.9.10-bin.zip
++ '[' -n ache.org/maven2/org/apache/maven/apache-maven/3.9.10/apache-maven-3.9.10-bin.zip ']'
++ char=a
+++ LC_CTYPE=C
+++ printf %d ''\''a'
++ h=3677627458
++ str=che.org/maven2/org/apache/maven/apache-maven/3.9.10/apache-maven-3.9.10-bin.zip
++ '[' -n che.org/maven2/org/apache/maven/apache-maven/3.9.10/apache-maven-3.9.10-bin.zip ']'
++ char=c
+++ LC_CTYPE=C
+++ printf %d ''\''c'
++ h=2337301601
++ str=he.org/maven2/org/apache/maven/apache-maven/3.9.10/apache-maven-3.9.10-bin.zip
++ '[' -n he.org/maven2/org/apache/maven/apache-maven/3.9.10/apache-maven-3.9.10-bin.zip ']'
++ char=h
+++ LC_CTYPE=C
+++ printf %d ''\''h'
++ h=3736872999
++ str=e.org/maven2/org/apache/maven/apache-maven/3.9.10/apache-maven-3.9.10-bin.zip
++ '[' -n e.org/maven2/org/apache/maven/apache-maven/3.9.10/apache-maven-3.9.10-bin.zip ']'
++ char=e
+++ LC_CTYPE=C
+++ printf %d ''\''e'
++ h=4173913374
++ str=.org/maven2/org/apache/maven/apache-maven/3.9.10/apache-maven-3.9.10-bin.zip
++ '[' -n .org/maven2/org/apache/maven/apache-maven/3.9.10/apache-maven-3.9.10-bin.zip ']'
++ char=.
+++ LC_CTYPE=C
+++ printf %d ''\''.'
++ h=542295760
++ str=org/maven2/org/apache/maven/apache-maven/3.9.10/apache-maven-3.9.10-bin.zip
++ '[' -n org/maven2/org/apache/maven/apache-maven/3.9.10/apache-maven-3.9.10-bin.zip ']'
++ char=o
+++ LC_CTYPE=C
+++ printf %d ''\''o'
++ h=3926266783
++ str=rg/maven2/org/apache/maven/apache-maven/3.9.10/apache-maven-3.9.10-bin.zip
++ '[' -n rg/maven2/org/apache/maven/apache-maven/3.9.10/apache-maven-3.9.10-bin.zip ']'
++ char=r
+++ LC_CTYPE=C
+++ printf %d ''\''r'
++ h=1455186099
++ str=g/maven2/org/apache/maven/apache-maven/3.9.10/apache-maven-3.9.10-bin.zip
++ '[' -n g/maven2/org/apache/maven/apache-maven/3.9.10/apache-maven-3.9.10-bin.zip ']'
++ char=g
+++ LC_CTYPE=C
+++ printf %d ''\''g'
++ h=2161096212
++ str=/maven2/org/apache/maven/apache-maven/3.9.10/apache-maven-3.9.10-bin.zip
++ '[' -n /maven2/org/apache/maven/apache-maven/3.9.10/apache-maven-3.9.10-bin.zip ']'
++ char=/
+++ LC_CTYPE=C
+++ printf %d ''\''/'
++ h=2569473179
++ str=maven2/org/apache/maven/apache-maven/3.9.10/apache-maven-3.9.10-bin.zip
++ '[' -n maven2/org/apache/maven/apache-maven/3.9.10/apache-maven-3.9.10-bin.zip ']'
++ char=m
+++ LC_CTYPE=C
+++ printf %d ''\''m'
++ h=2344257330
++ str=aven2/org/apache/maven/apache-maven/3.9.10/apache-maven-3.9.10-bin.zip
++ '[' -n aven2/org/apache/maven/apache-maven/3.9.10/apache-maven-3.9.10-bin.zip ']'
++ char=a
+++ LC_CTYPE=C
+++ printf %d ''\''a'
++ h=3952500591
++ str=ven2/org/apache/maven/apache-maven/3.9.10/apache-maven-3.9.10-bin.zip
++ '[' -n ven2/org/apache/maven/apache-maven/3.9.10/apache-maven-3.9.10-bin.zip ']'
++ char=v
+++ LC_CTYPE=C
+++ printf %d ''\''v'
++ h=2268434151
++ str=en2/org/apache/maven/apache-maven/3.9.10/apache-maven-3.9.10-bin.zip
++ '[' -n en2/org/apache/maven/apache-maven/3.9.10/apache-maven-3.9.10-bin.zip ']'
++ char=e
+++ LC_CTYPE=C
+++ printf %d ''\''e'
++ h=1601982046
++ str=n2/org/apache/maven/apache-maven/3.9.10/apache-maven-3.9.10-bin.zip
++ '[' -n n2/org/apache/maven/apache-maven/3.9.10/apache-maven-3.9.10-bin.zip ']'
++ char=n
+++ LC_CTYPE=C
+++ printf %d ''\''n'
++ h=2416803280
++ str=2/org/apache/maven/apache-maven/3.9.10/apache-maven-3.9.10-bin.zip
++ '[' -n 2/org/apache/maven/apache-maven/3.9.10/apache-maven-3.9.10-bin.zip ']'
++ char=2
+++ LC_CTYPE=C
+++ printf %d ''\''2'
++ h=1906457698
++ str=/org/apache/maven/apache-maven/3.9.10/apache-maven-3.9.10-bin.zip
++ '[' -n /org/apache/maven/apache-maven/3.9.10/apache-maven-3.9.10-bin.zip ']'
++ char=/
+++ LC_CTYPE=C
+++ printf %d ''\''/'
++ h=3265613837
++ str=org/apache/maven/apache-maven/3.9.10/apache-maven-3.9.10-bin.zip
++ '[' -n org/apache/maven/apache-maven/3.9.10/apache-maven-3.9.10-bin.zip ']'
++ char=o
+++ LC_CTYPE=C
+++ printf %d ''\''o'
++ h=2449781250
++ str=rg/apache/maven/apache-maven/3.9.10/apache-maven-3.9.10-bin.zip
++ '[' -n rg/apache/maven/apache-maven/3.9.10/apache-maven-3.9.10-bin.zip ']'
++ char=r
+++ LC_CTYPE=C
+++ printf %d ''\''r'
++ h=2928774832
++ str=g/apache/maven/apache-maven/3.9.10/apache-maven-3.9.10-bin.zip
++ '[' -n g/apache/maven/apache-maven/3.9.10/apache-maven-3.9.10-bin.zip ']'
++ char=g
+++ LC_CTYPE=C
+++ printf %d ''\''g'
++ h=597706679
++ str=/apache/maven/apache-maven/3.9.10/apache-maven-3.9.10-bin.zip
++ '[' -n /apache/maven/apache-maven/3.9.10/apache-maven-3.9.10-bin.zip ']'
++ char=/
+++ LC_CTYPE=C
+++ printf %d ''\''/'
++ h=1349037912
++ str=apache/maven/apache-maven/3.9.10/apache-maven-3.9.10-bin.zip
++ '[' -n apache/maven/apache-maven/3.9.10/apache-maven-3.9.10-bin.zip ']'
++ char=a
+++ LC_CTYPE=C
+++ printf %d ''\''a'
++ h=3165469705
++ str=pache/maven/apache-maven/3.9.10/apache-maven-3.9.10-bin.zip
++ '[' -n pache/maven/apache-maven/3.9.10/apache-maven-3.9.10-bin.zip ']'
++ char=p
+++ LC_CTYPE=C
+++ printf %d ''\''p'
++ h=3640280455
++ str=ache/maven/apache-maven/3.9.10/apache-maven-3.9.10-bin.zip
++ '[' -n ache/maven/apache-maven/3.9.10/apache-maven-3.9.10-bin.zip ']'
++ char=a
+++ LC_CTYPE=C
+++ printf %d ''\''a'
++ h=1179544506
++ str=che/maven/apache-maven/3.9.10/apache-maven-3.9.10-bin.zip
++ '[' -n che/maven/apache-maven/3.9.10/apache-maven-3.9.10-bin.zip ']'
++ char=c
+++ LC_CTYPE=C
+++ printf %d ''\''c'
++ h=2206141417
++ str=he/maven/apache-maven/3.9.10/apache-maven-3.9.10-bin.zip
++ '[' -n he/maven/apache-maven/3.9.10/apache-maven-3.9.10-bin.zip ']'
++ char=h
+++ LC_CTYPE=C
+++ printf %d ''\''h'
++ h=3965874591
++ str=e/maven/apache-maven/3.9.10/apache-maven-3.9.10-bin.zip
++ '[' -n e/maven/apache-maven/3.9.10/apache-maven-3.9.10-bin.zip ']'
++ char=e
+++ LC_CTYPE=C
+++ printf %d ''\''e'
++ h=2683028134
++ str=/maven/apache-maven/3.9.10/apache-maven-3.9.10-bin.zip
++ '[' -n /maven/apache-maven/3.9.10/apache-maven-3.9.10-bin.zip ']'
++ char=/
+++ LC_CTYPE=C
+++ printf %d ''\''/'
++ h=1569493577
++ str=maven/apache-maven/3.9.10/apache-maven-3.9.10-bin.zip
++ '[' -n maven/apache-maven/3.9.10/apache-maven-3.9.10-bin.zip ']'
++ char=m
+++ LC_CTYPE=C
+++ printf %d ''\''m'
++ h=1409660740
++ str=aven/apache-maven/3.9.10/apache-maven-3.9.10-bin.zip
++ '[' -n aven/apache-maven/3.9.10/apache-maven-3.9.10-bin.zip ']'
++ char=a
+++ LC_CTYPE=C
+++ printf %d ''\''a'
++ h=749810077
++ str=ven/apache-maven/3.9.10/apache-maven-3.9.10-bin.zip
++ '[' -n ven/apache-maven/3.9.10/apache-maven-3.9.10-bin.zip ']'
++ char=v
+++ LC_CTYPE=C
+++ printf %d ''\''v'
++ h=1769276025
++ str=en/apache-maven/3.9.10/apache-maven-3.9.10-bin.zip
++ '[' -n en/apache-maven/3.9.10/apache-maven-3.9.10-bin.zip ']'
++ char=e
+++ LC_CTYPE=C
+++ printf %d ''\''e'
++ h=3307949324
++ str=n/apache-maven/3.9.10/apache-maven-3.9.10-bin.zip
++ '[' -n n/apache-maven/3.9.10/apache-maven-3.9.10-bin.zip ']'
++ char=n
+++ LC_CTYPE=C
+++ printf %d ''\''n'
++ h=3762181346
++ str=/apache-maven/3.9.10/apache-maven-3.9.10-bin.zip
++ '[' -n /apache-maven/3.9.10/apache-maven-3.9.10-bin.zip ']'
++ char=/
+++ LC_CTYPE=C
+++ printf %d ''\''/'
++ h=663504781
++ str=apache-maven/3.9.10/apache-maven-3.9.10-bin.zip
++ '[' -n apache-maven/3.9.10/apache-maven-3.9.10-bin.zip ']'
++ char=a
+++ LC_CTYPE=C
+++ printf %d ''\''a'
++ h=3388779124
++ str=pache-maven/3.9.10/apache-maven-3.9.10-bin.zip
++ '[' -n pache-maven/3.9.10/apache-maven-3.9.10-bin.zip ']'
++ char=p
+++ LC_CTYPE=C
+++ printf %d ''\''p'
++ h=1972937852
++ str=ache-maven/3.9.10/apache-maven-3.9.10-bin.zip
++ '[' -n ache-maven/3.9.10/apache-maven-3.9.10-bin.zip ']'
++ char=a
+++ LC_CTYPE=C
+++ printf %d ''\''a'
++ h=1031531365
++ str=che-maven/3.9.10/apache-maven-3.9.10-bin.zip
++ '[' -n che-maven/3.9.10/apache-maven-3.9.10-bin.zip ']'
++ char=c
+++ LC_CTYPE=C
+++ printf %d ''\''c'
++ h=1912701342
++ str=he-maven/3.9.10/apache-maven-3.9.10-bin.zip
++ '[' -n he-maven/3.9.10/apache-maven-3.9.10-bin.zip ']'
++ char=h
+++ LC_CTYPE=C
+++ printf %d ''\''h'
++ h=3459166858
++ str=e-maven/3.9.10/apache-maven-3.9.10-bin.zip
++ '[' -n e-maven/3.9.10/apache-maven-3.9.10-bin.zip ']'
++ char=e
+++ LC_CTYPE=C
+++ printf %d ''\''e'
++ h=4154957595
++ str=-maven/3.9.10/apache-maven-3.9.10-bin.zip
++ '[' -n -maven/3.9.10/apache-maven-3.9.10-bin.zip ']'
++ char=-
+++ LC_CTYPE=C
+++ printf %d ''\''-'
++ h=4249633906
++ str=maven/3.9.10/apache-maven-3.9.10-bin.zip
++ '[' -n maven/3.9.10/apache-maven-3.9.10-bin.zip ']'
++ char=m
+++ LC_CTYPE=C
+++ printf %d ''\''m'
++ h=2889632315
++ str=aven/3.9.10/apache-maven-3.9.10-bin.zip
++ '[' -n aven/3.9.10/apache-maven-3.9.10-bin.zip ']'
++ char=a
+++ LC_CTYPE=C
+++ printf %d ''\''a'
++ h=3679255942
++ str=ven/3.9.10/apache-maven-3.9.10-bin.zip
++ '[' -n ven/3.9.10/apache-maven-3.9.10-bin.zip ']'
++ char=v
+++ LC_CTYPE=C
+++ printf %d ''\''v'
++ h=2387784624
++ str=en/3.9.10/apache-maven-3.9.10-bin.zip
++ '[' -n en/3.9.10/apache-maven-3.9.10-bin.zip ']'
++ char=e
+++ LC_CTYPE=C
+++ printf %d ''\''e'
++ h=1006879413
++ str=n/3.9.10/apache-maven-3.9.10-bin.zip
++ '[' -n n/3.9.10/apache-maven-3.9.10-bin.zip ']'
++ char=n
+++ LC_CTYPE=C
+++ printf %d ''\''n'
++ h=1148490841
++ str=/3.9.10/apache-maven-3.9.10-bin.zip
++ '[' -n /3.9.10/apache-maven-3.9.10-bin.zip ']'
++ char=/
+++ LC_CTYPE=C
+++ printf %d ''\''/'
++ h=1243477750
++ str=3.9.10/apache-maven-3.9.10-bin.zip
++ '[' -n 3.9.10/apache-maven-3.9.10-bin.zip ']'
++ char=3
+++ LC_CTYPE=C
+++ printf %d ''\''3'
++ h=4188071933
++ str=.9.10/apache-maven-3.9.10-bin.zip
++ '[' -n .9.10/apache-maven-3.9.10-bin.zip ']'
++ char=.
+++ LC_CTYPE=C
+++ printf %d ''\''.'
++ h=981211089
++ str=9.10/apache-maven-3.9.10-bin.zip
++ '[' -n 9.10/apache-maven-3.9.10-bin.zip ']'
++ char=9
+++ LC_CTYPE=C
+++ printf %d ''\''9'
++ h=352772744
++ str=.10/apache-maven-3.9.10-bin.zip
++ '[' -n .10/apache-maven-3.9.10-bin.zip ']'
++ char=.
+++ LC_CTYPE=C
+++ printf %d ''\''.'
++ h=2346020518
++ str=10/apache-maven-3.9.10-bin.zip
++ '[' -n 10/apache-maven-3.9.10-bin.zip ']'
++ char=1
+++ LC_CTYPE=C
+++ printf %d ''\''1'
++ h=4007159371
++ str=0/apache-maven-3.9.10-bin.zip
++ '[' -n 0/apache-maven-3.9.10-bin.zip ']'
++ char=0
+++ LC_CTYPE=C
+++ printf %d ''\''0'
++ h=3962856261
++ str=/apache-maven-3.9.10-bin.zip
++ '[' -n /apache-maven-3.9.10-bin.zip ']'
++ char=/
+++ LC_CTYPE=C
+++ printf %d ''\''/'
++ h=2589459850
++ str=apache-maven-3.9.10-bin.zip
++ '[' -n apache-maven-3.9.10-bin.zip ']'
++ char=a
+++ LC_CTYPE=C
+++ printf %d ''\''a'
++ h=2963844119
++ str=pache-maven-3.9.10-bin.zip
++ '[' -n pache-maven-3.9.10-bin.zip ']'
++ char=p
+++ LC_CTYPE=C
+++ printf %d ''\''p'
++ h=1684854585
++ str=ache-maven-3.9.10-bin.zip
++ '[' -n ache-maven-3.9.10-bin.zip ']'
++ char=a
+++ LC_CTYPE=C
+++ printf %d ''\''a'
++ h=690884680
++ str=che-maven-3.9.10-bin.zip
++ '[' -n che-maven-3.9.10-bin.zip ']'
++ char=c
+++ LC_CTYPE=C
+++ printf %d ''\''c'
++ h=4237555995
++ str=he-maven-3.9.10-bin.zip
++ '[' -n he-maven-3.9.10-bin.zip ']'
++ char=h
+++ LC_CTYPE=C
+++ printf %d ''\''h'
++ h=2515217069
++ str=e-maven-3.9.10-bin.zip
++ '[' -n e-maven-3.9.10-bin.zip ']'
++ char=e
+++ LC_CTYPE=C
+++ printf %d ''\''e'
++ h=662317912
++ str=-maven-3.9.10-bin.zip
++ '[' -n -maven-3.9.10-bin.zip ']'
++ char=-
+++ LC_CTYPE=C
+++ printf %d ''\''-'
++ h=3351986133
++ str=maven-3.9.10-bin.zip
++ '[' -n maven-3.9.10-bin.zip ']'
++ char=m
+++ LC_CTYPE=C
+++ printf %d ''\''m'
++ h=832355128
++ str=aven-3.9.10-bin.zip
++ '[' -n aven-3.9.10-bin.zip ']'
++ char=a
+++ LC_CTYPE=C
+++ printf %d ''\''a'
++ h=33205289
++ str=ven-3.9.10-bin.zip
++ '[' -n ven-3.9.10-bin.zip ']'
++ char=v
+++ LC_CTYPE=C
+++ printf %d ''\''v'
++ h=1029364077
++ str=en-3.9.10-bin.zip
++ '[' -n en-3.9.10-bin.zip ']'
++ char=e
+++ LC_CTYPE=C
+++ printf %d ''\''e'
++ h=1845515416
++ str=n-3.9.10-bin.zip
++ '[' -n n-3.9.10-bin.zip ']'
++ char=n
+++ LC_CTYPE=C
+++ printf %d ''\''n'
++ h=1376403158
++ str=-3.9.10-bin.zip
++ '[' -n -3.9.10-bin.zip ']'
++ char=-
+++ LC_CTYPE=C
+++ printf %d ''\''-'
++ h=4013792279
++ str=3.9.10-bin.zip
++ '[' -n 3.9.10-bin.zip ']'
++ char=3
+++ LC_CTYPE=C
+++ printf %d ''\''3'
++ h=4168476412
++ str=.9.10-bin.zip
++ '[' -n .9.10-bin.zip ']'
++ char=.
+++ LC_CTYPE=C
+++ printf %d ''\''.'
++ h=373749938
++ str=9.10-bin.zip
++ '[' -n 9.10-bin.zip ']'
++ char=9
+++ LC_CTYPE=C
+++ printf %d ''\''9'
++ h=2996313543
++ str=.10-bin.zip
++ '[' -n .10-bin.zip ']'
++ char=.
+++ LC_CTYPE=C
+++ printf %d ''\''.'
++ h=2691406663
++ str=10-bin.zip
++ '[' -n 10-bin.zip ']'
++ char=1
+++ LC_CTYPE=C
+++ printf %d ''\''1'
++ h=1829227978
++ str=0-bin.zip
++ '[' -n 0-bin.zip ']'
++ char=0
+++ LC_CTYPE=C
+++ printf %d ''\''0'
++ h=871492518
++ str=-bin.zip
++ '[' -n -bin.zip ']'
++ char=-
+++ LC_CTYPE=C
+++ printf %d ''\''-'
++ h=1246464327
++ str=bin.zip
++ '[' -n bin.zip ']'
++ char=b
+++ LC_CTYPE=C
+++ printf %d ''\''b'
++ h=4280655867
++ str=in.zip
++ '[' -n in.zip ']'
++ char=i
+++ LC_CTYPE=C
+++ printf %d ''\''i'
++ h=3851313102
++ str=n.zip
++ '[' -n n.zip ']'
++ char=n
+++ LC_CTYPE=C
+++ printf %d ''\''n'
++ h=3426589280
++ str=.zip
++ '[' -n .zip ']'
++ char=.
+++ LC_CTYPE=C
+++ printf %d ''\''.'
++ h=3145052622
++ str=zip
++ '[' -n zip ']'
++ char=z
+++ LC_CTYPE=C
+++ printf %d ''\''z'
++ h=3007350892
++ str=ip
++ '[' -n ip ']'
++ char=i
+++ LC_CTYPE=C
+++ printf %d ''\''i'
++ h=3033564541
++ str=p
++ '[' -n p ']'
++ char=p
+++ LC_CTYPE=C
+++ printf %d ''\''p'
++ h=3846187667
++ str=
++ '[' -n '' ']'
++ printf '%x\n' 3846187667
+ MAVEN_HOME=/home/skrambol/.m2/wrapper/dists/apache-maven-3.9.10/e5402a93
+ '[' -d /home/skrambol/.m2/wrapper/dists/apache-maven-3.9.10/e5402a93 ']'
+ case "${distributionUrl-}" in
++ mktemp -d
+ TMP_DOWNLOAD_DIR=/tmp/tmp.GjYofGHgWH
+ '[' -d /tmp/tmp.GjYofGHgWH ']'
+ trap clean HUP INT TERM EXIT
+ mkdir -p -- /home/skrambol/.m2/wrapper/dists/apache-maven-3.9.10
+ verbose 'Couldn'\''t find MAVEN_HOME, downloading and installing it ...'
+ :
+ verbose 'Downloading from: https://repo.maven.apache.org/maven2/org/apache/maven/apache-maven/3.9.10/apache-maven-3.9.10-bin.zip'
+ :
+ verbose 'Downloading to: /tmp/tmp.GjYofGHgWH/apache-maven-3.9.10-bin.zip'
+ :
+ command -v unzip
+ __MVNW_QUIET_WGET=--quiet
+ __MVNW_QUIET_CURL=--silent
+ __MVNW_QUIET_UNZIP=-q
+ __MVNW_QUIET_TAR=
+ '[' '' '!=' true ']'
+ case "${MVNW_PASSWORD:+has-password}" in
+ MVNW_USERNAME=
+ MVNW_PASSWORD=
+ '[' -z '' ']'
+ command -v wget
+ verbose 'Found wget ... using wget'
+ :
+ wget --quiet https://repo.maven.apache.org/maven2/org/apache/maven/apache-maven/3.9.10/apache-maven-3.9.10-bin.zip -O /tmp/tmp.GjYofGHgWH/apache-maven-3.9.10-bin.zip
^C++ clean
++ rm -rf -- /tmp/tmp.GjYofGHgWH
+ die 'wget: Failed to fetch https://repo.maven.apache.org/maven2/org/apache/maven/apache-maven/3.9.10/apache-maven-3.9.10-bin.zip'
+ printf '%s\n' 'wget: Failed to fetch https://repo.maven.apache.org/maven2/org/apache/maven/apache-maven/3.9.10/apache-maven-3.9.10-bin.zip'
wget: Failed to fetch https://repo.maven.apache.org/maven2/org/apache/maven/apache-maven/3.9.10/apache-maven-3.9.10-bin.zip
+ exit 1
+ clean
+ rm -rf -- /tmp/tmp.GjYofGHgWH

```
- wget error is still visible since i cancelled it. further checked the script and there was an option for verbosity
- based on [this website](https://tldp.org/LDP/Bash-Beginners-Guide/html/sect_02_03.html)

useful in checking what line/code the bash script is executing