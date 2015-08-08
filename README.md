# CDH-Cluster-Install

## <center> Cloudera Manager Install
## <center> <a name="linux_config_check"/>Linux Configuration Check

This checklist uses a [presentation on Slideshare](http://tiny.cloudera.com/7steps) and is a small sample of an install precheck. 

1. Check swappiness on all your nodes, then set the recommended value
 * Set the value to 1 for current and future boots
2. Set <code>noatime</code> on DN volumes
 * For labs, do this on your root volume 
3. Set reserve space for root on DN volumes to 0
 * For labs, do this on your root volume
4. Check the user resource limits for max file descriptors and processes
5. Test forward and reverse lookups for both file-based and DNS name services
 a. Note: <code>/etc/hosts</code>, the [FQDN](https://en.wikipedia.org/wiki/Fully_qualified_domain_name) must be listed first  
 b. Note: <code>127.0.0.1</code> **must** resolve to <code>localhost</code>
6. Enable nscd
 a. Note: consult documentation before [running nscd with SSSD](http://goo.gl/68HTMQ)

---
<div style="page-break-after: always;"></div>


[root@wertz-sebc-5 ~]# history

1.  lscpu
2.  cat /proc/sys/vm/swappiness 
3.  more /etc/sysctl.conf 
4.  df -h
5.  clear
6.  cat /proc/sys/vm/swappiness
7.  vi /etc/sysctl.conf 
8.  shutdown -r now
9.  clear
10.  cat /proc/sys/vm/swappiness 
11.  more /etc/nfsmount.conf 
12.  more /etc/init.d/
13.  cleqr
14.  clear
15.  more /etc/fstab 
16.  vi /etc/fstab 
17.  shutdown -r now
18.  vi /etc/fstab 
19.  shutdown -r now
20.  clear
21.  cat /proc/mounts 
22.  clear
23.  ulimit -a
24.  clear
25.  more /etc/hosts
26.  vi /etc/hosts
27.  clear
28.  cat /etc/hosts
29.  service network restart
30.  info nscd
31.  ps -a
32.  ps -au
33.  ps -help
34.  ps -A
35.  ps -A | grep -i sssd
36.  more /etc/sssd/
37.  ll /etc/sssd/
38.  ll /var/lib/sss/db/
39.  ls -al /var/lib/sss/db/
40.  serice sssd status
41.  service sssd status
42.  clear
43.  service sssd status
44.  service nscd status
45.  service nscd start
46.  service nscd status
47.  clear
48.  service nscd status
49.  lscpu 
50.  yum install mysql-server
51.  service mysqld stop
52.  ls /var/lib/mysql/
53.  ll /var/lib/mysql/
54.  more /etc/my.cnf 
55.  clear
56.  more /etc/my.cnf 
57.  vi /etc/my.cnf 
58.  clear
59.  more /etc/my.cnf 
60.  service apparmor status
61.  /sbin/chkconfig mysqld on
62.  /sbin/chkconfig --list mysqld
63.  service mysqld start
64.  service mysqld --log-bin start
65.  service mysqld start --log-bin
66.  service mysqld start
67.  service mysqld stop
68.  tree /var/lib/m
69.  tree /var/lib/mysql/
70.  yum install tree
71.  tree /var/lib/mysql/
72.  more /etc/my.cnf 
73.  which mysql
74.  mysql --version
75.  vi /etc/my.cnf 
76.  service mysqld start
77.  more /var/log/mysqld.log 
78.  mysql_upgrade
79.  yum remove mysql*
80.  rm -rf /usr/bin/mysql
81.  rm -rf /var/lib/mysql
82.  more /etc/my.cnf.rpmsave 
83.  rm /etc/my.cnf.rpmsave
84.  ps -e
85.  ps -e | grep -i mysql
86.  shutdown -r now
87.  ll
88.  yum install mysql
89.  yum install mysql-server
90.  wget http://dev.mysql.com/downloads/file.php?id=457911
91.  ll
92.  more file.php\?id\=457911 
93.  ll
94.  rm file.php\?id\=457911 
95.  wget http://dev.mysql.com/get/Downloads/Connector-J/mysql-connector-java-5.1.36.tar.gz
96.  ll
97.  vi /etc/my.cnf 
98.  more /var/lib/mysql/
99.  ll /var/lib/mysql/
100.  mysql_install_db
101.  /usr/bin/mysql_secure_installation
102.  /usr/bin/mysqld_safe &
103.  ps -E
104.  history | grep ps
105.  ps -e
106.  ps -e | grep mysql
107.  ps -e | grep mysql*
108.  more /var/log/mysqld.log
109.  service mysqld start
110.  cd /usr
111.  ll
112.  /usr/bin/mysqld_safe &
113.  ps -e | grep mysql*
114.  more /var/log/mysqld.log
115.  more /etc/my.cnf
116.  vi /etc/my.cnf
117.  cd /var/lib/mysql/
118.  ll
119.  ll mysql
120.  more /var/log/mysqld.log
121.  chown -R /var/lib/mysql/
122.  chown -R mysql /var/lib/mysql/
123.  /usr/bin/mysqld_safe &
124.  ps -e | grep mysql*
125.  ll
126.  pwd
127.  /usr/bin/mysql_secure_installation
128.  mysql -u root -pcloudera
129.  exit
130.  mysql -u root -pcloudera
131.  exit
132.  clear
133.  history
134.  exit
135.  wget http://archive.cloudera.com/cm5/redhat/6/x86_64/cm/cloudera-manager.repo
136.  mv cloudera-manager.repo /etc/yum.repos.d/
137.  ll /etc/yum.repos.d/
138.  java -version
139.  java
140.  yum install oracle-j2sdk1.7
141.  java -version
142.  which java
143.  find / -name java
144.  ll /usr/java/
145.  ll /usr/share/java
146.  ll /usr/java/jdk1.7.0_67-cloudera/bin/java
147.  /usr/java/jdk1.7.0_67-cloudera/bin/java
148.  /usr/java/jdk1.7.0_67-cloudera/bin/java -version
149.  yum install cloudera-manager-daemons cloudera-manager-server
150.  service cloudera-scm-server start
151.  more /var/log/cloudera-scm-server/cloudera-scm-server.log 
152.  ll
153.  tar -xzf mysql-connector-java-5.1.36.tar.gz 
154.  ll
155.  ll mysql-connector-java-5.1.36
156.  yum install mysql-connector-java
157.  service cloudera-scm-server start
158.  tail -f /var/log/cloudera-scm-server/cloudera-scm-server.log 
159.  ll
160.  find / -name mysql-connector-java *
161.  find / -name mysql-connector-java*
162.  find / -name "mysql-connector-java*"
163.  pwd
164.  ll /usr/share/java
165.  yum remove mysql-connector-java
166.  ll
167.  ll /usr/share/java/mysql*
168.  cp mysql-connector-java-5.1.36/mysql-connector-java-5.1.36-bin.jar /usr/share/java
169.  ln -s /usr/share/java/mysql-connector-java-5.1.36-bin.jar /usr/share/java/mysql-connector-java.jar 
170.  tail -f /var/log/cloudera-scm-server/cloudera-scm-server.log 
171.  service cloudera-scm-server stop
172.  service cloudera-scm-server start
173.  tail -f /var/log/cloudera-scm-server/cloudera-scm-server.log 
174.  /usr/bin/mysql_secure_installation
175.  which scm_prepare_database.sh 
176.  ls /usr/share/cmf/schema/scm_prepare_database.sh 
177.  /usr/share/cmf/schema/scm_prepare_database.sh
178.  /usr/share/cmf/schema/scm_prepare_database.sh mysql -uroot -pcloudera scm scm scm
179.  service cloudera-scm-server start
180.  tail -f /var/log/cloudera-scm-server/cloudera-scm-server.log 
181.  history
182.  exit
183.  mysql -u root -pcloudera
184.  exit
185.  mysql -uroot -pcloudera
186.  find / -name scm-agent
187.  find / -name *.xml
188.  find / -name *.xml | grep process
189.  clear
190.  history
191.  exit
192.  clear
193.  hdparm -t /dev/xvda1
194.  more /etc/my.cnf 
195.  mysql -u root -pcloudera
196.  hadoop jar hadoop-*examples*.jar teragen 10 /tmp
197.  groupadd cloudera
198.  useradd -g cloudera christoph
199.  passwd christoph
200.  useradd -g cloudera ashok
201.  passwd ashok
202.  mysql -uroot -p
203.  exit
204.  vi /etc/my.cnf 
205.  clear
206.  top
207.  wget https://github.com/mfernest/SEBC/blob/master/yarn/YARNtest.sh
208.  ll
209.  vi YARNtest.sh
210.  chmod +x YARNtest.sh 
211.  ll
212.  vi YARNtest.sh 
213.  ./YARNtest.sh 
214.  vi YARNtest.sh 
215.  echo $HADOOP_PATH
216.  more YARNtest.sh 
217.  vi YARNtest.sh 
218.  ./YARNtest.sh 
219.  vi YARNtest.sh 
220.  ./YARNtest.sh 
221.  vi YARNtest.sh 
222.  ./YARNtest.sh 
223.  vi YARNtest.sh 
224.  ./YARNtest.sh 
225.  ls =/opt/cloudera/parcels/CDH/lib/
226.  ls /opt/cloudera/parcels/CDH/lib/
227.  vi YARNtest.sh 
228.  su christoph
229.  ll
230.  cp YARNtest.sh /home/christoph/
231.  su
232.  su - christoph
233.  chown christoph:cloudera /home/christoph/YARNtest.sh 
234.  ll /home/christoph/
235.  su - christoph
236.  ll
237.  rm *.err
238.  rm -f *.err
239.  rm-f *.out
240.  ll
241.  rm -f *.out
242.  ll
243.  exit
244.  ll
245.  vi YARNtest.sh 
246.  ./YARNtest.sh 
247.  ll
248.  rm YARNtest.sh 
249.  su - christoph
250.  find / -name us_export_policy.jar
251.  find / -name local_policy.jar
252.  jar -tvf /usr/java/jdk1.6.0_31/jre/lib/security/local_policy.jar
253.  tar -tvf /usr/java/jdk1.6.0_31/jre/lib/security/local_policy.jar
254.  which jar
255.  yum install jdk
256.  hwich jar
257.  which jar
258.  find / -name jar
259.  /usr/java/jdk1.6.0_31/bin/jar
260.  /usr/java/jdk1.6.0_31/bin/jar -tvf /usr/java/jdk1.6.0_31/jre/lib/security/local_policy.jar
261.  ll
262.  mkdir security_policy
263.  cd security_policy/
264.  /usr/java/jdk1.6.0_31/bin/jar -xvf /usr/java/jdk1.6.0_31/jre/lib/security/local_policy.jar
265.  ll
266.  ll META-INF/
267.  more META-INF/MANIFEST.MF 
268.  ll
269.  more default_local.policy 
270.  ll
271.  cd META-INF/
272.  ll
273.  more JCE_RSA.RSA 
274.  ll
275.  more JCE_RSA.SF 
276.  cd
277.  ll
278.  cd security_policy/
279.  ll
280.  nmap -sT -O localhost
281.  /sbin/nmap
282.  yum install nmap
283.  which nmap
284.  nmap -sT -O localhost
285.  nmap -sT -O http://wertz-sebc-5.vpc.cloudera.com/
286.  nmap -sT -O wertz-sebc-5.vpc.cloudera.com
287.  ll
288.  wget http://web.mit.edu/kerberos/dist/krb5/1.13/krb5-1.13.2-signed.tar
289.  wget http://web.mit.edu/kerberos/dist/krb5-appl/1.0/krb5-appl-1.0.3-signed.tar
290.  ll
291.  tar -tvf krb5-1.13.2-signed.tar 
292.  tar -xvf krb5-1.13.2-signed.tar
293.  ll
294.  more krb5-1.13.2.tar.gz.asc 
295.  ll
296.  tar -xzf krb5-1.13.2.tar.gz
297.  ll
298.  tar -xvf krb5-appl-1.0.3-signed.tar 
299.  mroe krb5-appl-1.0.3.tar.gz.asc 
300.  more krb5-appl-1.0.3.tar.gz.asc
301.  tar -xzf krb5-appl-1.0.3.tar.gz
302.  ll
303.  cd krb5-1.13.2
304.  ll
305.  more README 
306.  ll
307.  cd src/
308.  ll
309.  ./configure 
310.  yum install gcc
311.  ./configure 
312.  make
313.  ;yum install yacc
314.  yum install yacc
315.  yum whatprovides byacc
316.  yum install byacc
317.  which yacc
318.  make
319.  make install
320.  make check
321.  ll
322.  make check -v
323.  make -v check
324.  make check
325.  find / -name uuserver
326.  info uuserver
327.  uuserver -help
328.  yum whatprovides kerberos
329.  yum install kerberos
330.  yum install krb5-server krb5-libs krb5-auth-dialog
331.  more /etc/krb5.conf 
332.  /usr/sbin/kdb5_util create -s
333.  vi /var/kerberos/krb5kdc/kadm5.acl 
334.  /usr/sbin/kadmin.local -q "addprinc admin/admin"
335.  /sbin/service krb5kdc start
336.  /sbin/service kadmin start
337.  /sbin/service krb5kdc status
338.  /sbin/service kadmin status
339.  kinit
340.  kinit admin/admin
341.  tcpdump udp port 88 
342.  ll
343.  kinit admin/admin
344.  more /etc/krb5.conf 
345.  kinit admin
346.  kinit admin@EXAMPLE.COM
347.  /sbin/ifconfig 
348.  vi /etc/hosts
349.  /sbin/service krb5kdc restart
350.  /sbin/service kadmin restart
351.  kinit admin@EXAMPLE.COM
352.  kinit -v admin@EXAMPLE.COM
353.  kinit -help
354.  kinit -V admin@EXAMPLE.COM
355.  ping example.com
356.  more /etc/krb5.conf 
357.  more /var/log/kadmind.log 
358.  more /var/log/krb5kdc.log 
359.  yum install openldap-clients
360.  yum install krb5-workstation, krb5-libs
361.  yum install krb5-workstation krb5-libs
362.  /usr/sbin/kadmin.local -q "addprinc -pw cloudera cloudera-scm/admin@EXAMPLE.COM"
363.  kinit cloudera-scm/admin@EXAMPLE.COM
364.  kinit -V cloudera-scm/admin@EXAMPLE.COM
365.  kinit
366.  klist
367.  export KRB5_TRACE=/dev/stderr
368.  echo $HADOOP_OPTS
369.  e
370.  export HADOOP_OPTS=-Dsun.security.krb5.debug=true
371.  echo $HADOOP_OPTS
372.  more /etc/krb5.conf 
373.  hostname
374.  vi /etc/krb5.conf 
375.  history | grep service
376.  /sbin/service krb5kdc restart
377.  /sbin/service kadmin restart
378.  kinit -V
379.  kinit scm-admin/admin@EXAMPLE.COM
380.  kinit cloudera-SCM/admin@EXAMPLE.COM
381.  kinit cloudera-scm/admin@EXAMPLE.COM
382.  cat /etc/krb5.conf 
383.  for i in 1 2 3 4; do echo $i; done
384.  for i in 1 2 3 4; do rsync /etc/krb5.conf root@wertz-sebc-$i.vpc.cloudera.com:/etc/krb5.conf; done
385.  klist
386.  cat /etc/krb5.conf 
387.  hostname
388.  more /var/log/krb5kdc.log 
389.  grep vpc.cloudera.com /var/log/krb5kdc.log
390.  grep vpc.cloudera.com /var/log/krb5kdc.log | cut -d','
391.  grep vpc.cloudera.com /var/log/krb5kdc.log | cut -d',' -f1-3
392.  grep vpc.cloudera.com /var/log/krb5kdc.log | cut -d',' -f2
393.  grep vpc.cloudera.com@EXAMPLE.COM /var/log/krb5kdc.log | cut -d',' -f2
394.  grep vpc.cloudera.com /var/log/krb5kdc.log | cut -d',' -f2
395.| grep -v closing
396.  grep vpc.cloudera.com /var/log/krb5kdc.log | cut -d',' -f2 | grep -v closing
397.  grep vpc.cloudera.com /var/log/krb5kdc.log | cut -d',' -f2 | grep -v closing | grep -v etypes
398.  klist
399.  clear
400.  klist
401.  more /tmp/krb5cc_0 
402.  cler
403.  clear
404.  more /tmp/krb5cc_0 
405.  clear
406.  klist
407.  more /tmp/krb5cc_0 
408.  clear && klist
409.  klist -f
410.  ll
411.  ll -a
412.  cd
413.  ll
414.  ls -a
415.  ll -a
416.  pwd
417.  ll
418.  ll -a
419.  kinit
420.  hdfs dfs -ls
421.  hdfs dfs -ls /
422.  su christoph
423.  su hdfs
424.  kadmin
425.  su christoph
426.  kadmin
427.  su hue
428.  whoami
429.  more /var/kerberos/krb5kdc/kdc.conf 
430.  vi /var/kerberos/krb5kdc/kdc.conf
431.  history | grep service
432.  /sbin/service krb5kdc restart
433.  /sbin/service kadmin restart
434.  klist --help
435.  klist hue/wertz-sebc-5.vpc.cloudera.com@EXAMPLE.COM
436.  hdfs dfs -ls
437.  hdfs dfs -ls /
438. hdfs dfs -ls /user
439.  hdfs dfs -ls /user/christoph
440.  clear
441.  ll
442.  echo foo > foo.txt
443.  ll
444.  hdfs dfs -put foo.txt 
445.  mv foo.txt /home/christoph/
446.  shown christoph:cloudera /home/christoph/foo.txt 
447.  chown christoph:cloudera /home/christoph/foo.txt 
448.  su - christoph
449.  su - hue
450.  pwd
451.  whoami
452.  useradd -g cloudera hue
453.  su hue
454.  whoami
455.  kinit -f -c /tmp/hue_krb5_ccache
456.  klist hue/wertz-sebc-5.vpc.cloudera.com@EXAMPLE.COM
457.  klist
458.  ll /tmp/
459.  ll /tmp/*krb*
460.  klist -k /tmp/hue_krb5_ccache 
461.  klist -A
462.  kadmin
463.  sqlite3 /var/lib/hue/desktop.db
464.  ll
465.  hdfs df -ls /user
466.  hdfs dfs -ls /user
467.  ls /mnt/yarn/nm/usercache/christoph/appcache
468.  ls /mnt/yarn/nm/usercache/christoph/
469. ls /mnt/yarn
470.  clear
471.  ll /mnt/yarn/nm/usercache/christoph/
472.  more  /var/run/cloudera-scm-agent/process/209-hue-HUE_SERVER
473.  ll /var/run/cloudera-scm-agent/process/209-hue-HUE_SERVER
474.  cd /var/run/cloudera-scm-agent/process/209-hue-HUE_SERVER
475.  ll
476.  more cloudera-monitor.properties 
477.  ll hive-conf/
478.  cd
479.  su christoph
480.  yum install git
481.  su christoph
482.  vi /etc/yum.repos.d/cloudera-cdh5.repo
483.  more /etc/hue/conf/hue.ini 
484.  kadmin.local: modprinc -maxrenewlife 90day krbtgt/EXAMPLE.COM
485.  kadminl.local
486.  kadmin.local
487.  kadmin.local: modprinc -maxrenewlife 90day krbtgt/EXAMPLE.COM
488.  kadmin.local modprinc -maxrenewlife 90day krbtgt/EXAMPLE.COM
489.  kadmin.local
490.  kadmin
491.  more /etc/hue/conf/hue.ini 
492.  clear
493.  mysql -u root -pcloudera
494.  mysql -u amon -pamon_password
495.  mysql -u root -pcloudera
496.  hdfs dfs -ls -R /user/hive
497.  klist
498.  beeline
499.  klist
500.  su christoph
501.  kadmin
502.  history
503.  exit
504.  clear
505.  history | grep mysql-connector
506.  clear
507.  history | grep mysql
508.  mysql -u root -pcloudera
509.  more /etc/host
510.  more /etc/hosts
511.  s
512.  more /etc/hosts
513.  solr
514.  clear
515.  spark-shell
516.  which sbt
517.  hdfs dfs -ls /user
518.  kinit
519.  su - christoph
520.  history
[root@wertz-sebc-5 ~]# 
