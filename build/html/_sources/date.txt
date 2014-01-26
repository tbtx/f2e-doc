date
===============

日期相关

date均可以为字符串，数字或者date对象

* formatDate([format[, date]])

"Y-m-d h:i:s" 按format格式化日期

* normalDate(date)

将date转为对象，包含Y-M-D-H-I-S-y-m-d-h-i-s

* ago(date1[, date2])

对比两个时间，输出刚刚/分钟前/小时前/天前/月前/年前

    /*
     * 将日期格式化成字符串
     *  Y - 4位年
     *  y - 2位年
     *  M - 不补0的月,
     *  m - 补0的月
     *  D - 不补0的日期
     *  d - 补0的日期
     *  H - 不补0的小时
     *  h - 补0的小时
     *  I - 不补0的分
     *  i - 补0的分
     *  S - 不补0的秒
     *  s - 补0的秒
     *  毫秒暂不支持
     *  @return：指定格式的字符串
     */