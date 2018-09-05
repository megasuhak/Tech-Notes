
#### PHP显示一段代码的执行时间

```
$start_time = microtime(true);

// 这里开始你要执行的代码，code begin
for ($i = 0; $i<10; $i++) {
     echo $i . '<br>';
}
// code end

$end_time = microtime(true);
echo '程序耗时 ' . number_format(($end_time - $start_time), 9) . ' 秒';
echo '<br>';
echo '程序耗时 ' . round($end_time - $start_time, 3) . ' 秒';
```
