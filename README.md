
* [(Fuse) ActiveMQ Tuning Guide](https://access.redhat.com/documentation/en-US/Fuse_ESB_Enterprise/7.1/html-single/ActiveMQ_Tuning_Guide/index.html)
* [Monitor ActiveMQ metrics and performance](https://www.datadoghq.com/blog/monitor-activemq-metrics-performance)
  * **(** [mail.google.com](https://mail.google.com/mail/u/0/#inbox/FMfcgxwBVDCvxfCPQXBQKwLsQgKnJzTn) **)**
  * [Installing on Windows](https://app.datadoghq.com/signup/agent#windows) `skmets@gmail.com / a***n`
    ```bash
    msiexec /qn /i datadog-agent-6-latest.amd64.msi APIKEY="43badebfebd35f7401abc04748d758c9" HOSTNAME="my_hostname" TAGS="mytag1,mytag2"
    ```
* [Running Apache ActiveMQ and Hawtio in Standalone Mode](http://bennet-schulz.com/2016/07/apache-activemq-and-hawtio.html)
  * **(** https://dzone.com/articles/running-apache-activemq-and-hawtio-in-standalone-m-1 **)**
  * https://github.com/bennetelli/activemq-hawtio-standalone


Setting JDBC SQL Server Connection with JMeter
---

* `Can JMeter be used to delete records from a database?` https://stackoverflow.com/questions/22021865/can-jmeter-be-used-to-delete-records-from-a-database
  ```text
  You must choose Callable Statement in JDBC Request as  delete from Stocks where StockIdent=1
  ```

* https://habr.com/ru/post/261483
* `https://performancebasics.wordpress.com/2016/01/25/setting-up-a-jdbc-sql-server-connection-in-jmeter`
* https://www.blazemeter.com/blog/how-to-retrieve-database-data-for-api-testing-with-jmeter



* `Assertion on JMeter JDBC Request sampler` https://stackoverflow.com/questions/24133498/assertion-on-jmeter-jdbc-request-sampler
* `How to Retrieve Database Data for API Testing with JMeter` https://www.blazemeter.com/blog/how-to-retrieve-database-data-for-api-testing-with-jmeter

* `JMeter: забудьте про BeanShell Sampler` https://habr.com/ru/post/250731
* http://performanceoptimize.blogspot.com/2017/05/TimeFucntionInJmeter.html
    ```java
    import java.text.SimpleDateFormat;
    import java.util.Calendar;
    import java.util.Date;
    
    
    Date tokenStatusUpdate = token.get("token_status_update");
    
    int AddSeconds = 01;
    int AddMinutes = 00;
    int AddHours   = 00;
    
    Date now       = new Date();
    Calendar c     = Calendar.getInstance();
    c.setTime(now);
    c.add(Calendar.SECOND, AddSeconds);
    c.add(Calendar.MINUTE, AddMinutes);
    c.add(Calendar.HOUR,   AddHours);
    SimpleDateFormat df = new SimpleDateFormat("HH:mm:ss");
    //String mytime       = df.format(now);
    
    Date nowTime        = c.getTime();
    String mytime       = df.format(nowTime);
    
    FailureMessage = "'token_status_update': " + mytime;
    
    String srtTokenStatusUpdate = df.format(tokenStatusUpdate);
    
    long timeTokenStatusUpdate = tokenStatusUpdate.getTime() / 100;
    long timeNow = (now.getTime() - 100) / 100;
    FailureMessage = "'token_status_update': " + timeTokenStatusUpdate + " --- " + timeNow;
    
  //FailureMessage = "'token_status_update': " + ${__time(/1000,)};
    ```


How to Run External Commands and Programs from JMeter
---
* `run sh script in jmeter` https://stackoverflow.com/questions/30596880/run-sh-script-in-jmeter
                            https://www.blazemeter.com/blog/how-run-external-commands-and-programs-locally-and-remotely-jmeter
* `How to execute jar from OS Process Sampler in Linux` https://stackoverflow.com/questions/38181399/how-to-execute-jar-from-os-process-sampler-in-linux
* `How to Run External Commands and Programs Locally and Remotely from JMeter` https://www.blazemeter.com/blog/how-run-external-commands-and-programs-locally-and-remotely-jmeter



* `https://www.blazemeter.com/blog/creating-and-testing-dates-in-jmeter-learn-how`
* `https://stackoverflow.com/questions/27043029/jmeter-get-current-date-and-time/27048364`
* `https://stackoverflow.com/questions/42364226/jmeter-how-to-get-current-date-and-time-in-seconds`

---

* `JMETER VS SOAPUI` https://octoperf.com/blog/2018/06/05/jmeter-vs-soapui/


* `How to Use JMeter Assertions in Three Easy Steps` https://www.blazemeter.com/blog/how-use-jmeter-assertions-three-easy-steps


* `how to empty or truncate a file in linux` http://www.lostsaloon.com/technology/how-to-empty-or-truncate-files-in-linux
* `Просмотр текстовых файлов` http://www.linuxcookbook.ru/books/opensuse/sec.new.bash.view.html



|   | windows  |
|---|---|
| serverUrl  | 192.168.1.113  |
| start_time  | ${__time(YMDHMS)}  |
| testPlanUrl  | ${__BeanShell(import org.apache.jmeter.services.FileServer; FileServer.getFileServer().getBaseDir();)}  |
| correlationIDFile  | ${__BeanShell(import org.apache.jmeter.services.FileServer; FileServer.getFileServer().getBaseDir();)}\start_correlationID  |
| tokenReferenceIDFile  | ${__BeanShell(import org.apache.jmeter.services.FileServer; FileServer.getFileServer().getBaseDir();)}\start_tokenReferenceID  |
| nmon_start_time  | ${__time(yyyy-MM-dd'T'HH:mm:ss,)}  |
| resultDir  | ${__BeanShell(import org.apache.jmeter.services.FileServer; FileServer.getFileServer().getBaseDir();)}\results\\${__time(YMDHMS)}  |


|   | linux  |
|---|---|
| serverUrl  | 192.168.1.113  |
| start_time  | ${__time(YMDHMS)}  |
| testPlanUrl  | ${__BeanShell(import org.apache.jmeter.services.FileServer; FileServer.getFileServer().getBaseDir();)}  |
| correlationIDFile  | ${__BeanShell(import org.apache.jmeter.services.FileServer; FileServer.getFileServer().getBaseDir();)}/conf/start_correlationId.conf  |
| tokenReferenceIDFile  | ${__BeanShell(import org.apache.jmeter.services.FileServer; FileServer.getFileServer().getBaseDir();)}/conf/start_tokenReferenceId.conf  |
| nmon_start_time  | ${__time(yyyy-MM-dd'T'HH:mm:ss,)}  |
| resultDir  | ${__BeanShell(import org.apache.jmeter.services.FileServer; FileServer.getFileServer().getBaseDir();)}/results/${__time(YMDHMS)}  |

