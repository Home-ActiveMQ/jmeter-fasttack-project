

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


* `https://www.blazemeter.com/blog/creating-and-testing-dates-in-jmeter-learn-how`
* `https://stackoverflow.com/questions/27043029/jmeter-get-current-date-and-time/27048364`
* `https://stackoverflow.com/questions/42364226/jmeter-how-to-get-current-date-and-time-in-seconds`

---

* `JMETER VS SOAPUI` https://octoperf.com/blog/2018/06/05/jmeter-vs-soapui/
