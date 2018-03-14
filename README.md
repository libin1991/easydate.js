# easydate.js

一款简易实用的日期时间操作函数！

## 使用easydate

### 使用`easydate`函数创建实例


```js

// 给定日期字符串
const edate = easydate('2018/03/17 16:08:32');

// 给定时间戳
const edate2 = easydate(1521274112000);

// 给定已有日期对象
const edate3 = easydate(new Date());

// 默认当前系统时间
const edate4 = easydate();

```

### 获取日期时间的信息部分

```js

// (Date) 日期对象
edate.date;

// (boolean) 判断日期时间的有效性
// true
edate.isValid();

// (boolean) 判断是否是闰年
// flase
edate.isLeapYear();

// (number) 返回毫秒级快照
// 1521274112000
edate.valueOf();

// (number) 返回年份
// 2018
edate.getFullYear();

// (number) 返回月份，月份值从1~12
// 3
edate.getMonth();

// (number) 返回当月的第几天
// 17
edate.getDate();

// (number) 返回当周的第几天，值从0~6表示周日~周六
// 6
edate.getDay();

// (number) 返回时钟
// 16
edate.getHours();

// (number) 返回分钟
// 8
edate.getMinutes();

// (number) 返回秒钟
// 32
edate.getSeconds(); 

// (number) 返回毫秒数
// 0
edate.getMilliseconds();

```

### 日期时间的格式化输出

```js

// 返回日期时间的字符串表示 '2018/03/17 16:08:32'
// 等同于.format()、.format('yyyy-MM-dd HH:mm:ss')
edate.toString();

// 格式化输出 '2018/03/17 16:08:32'
// 等同于.format('yyyy-MM-dd HH:mm:ss')
edate.format();

// 格式化输出 '18/3/17 16:8:32'
edate.format('yy-M-d H:m:s');

// 格式化输出 '2018/03/17 16:08:32'
edate.format('yyyy-MM-dd HH:mm:ss');

// 格式化输出 '2018年03月17日 下午 04:08:32'
edate.format('yyyy年MM月dd日 tt hh:mm:ss');

```

### 日期时间的计算

```js

// 秒钟+1
// 2018/03/17 16:08:33
edate.calc('second', 1);

// 分钟+1
// 2018/03/17 16:09:33
edate.calc('minute', 1);

// 时钟+1
// 2018/03/17 17:09:33
edate.calc('hour', 1);

// 天数+1
// 2018/03/18 17:09:33
edate.calc('day', 1);

// 月份+1
// 2018/04/18 17:09:33
edate.calc('month', 1);

// 年份+1
// 2019/04/18 17:09:33
edate.calc('year', 1);

// 截取日期部分
// 2018/04/18 00:00:00
edate.toDatePart();   

```

### 链式操作


```js

// output: 2018/03/23 12:00:00
easydate('2018/03/17 16:08:32').toDatePart().calc('day', 6).calc('hour', 12).format();

```
