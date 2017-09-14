1. 查看进程信息
```
ps -aux
```
2. awk跳过空白行后进行排序
```
cat text.txt| awk '{if(length($0)>0) print $0}' | sort -k2
```
3.对文件进行切分后删除字符按行输出
```
sample like this
com.miui.video
com.tencent.qqlive

'com.miui.video', 'com.tencent.qqlive', 'com.yidian.xiaomi', 'com.tencent.news', 'com.qiyi.video', 'com.android.browser' 
```

```
cat out.txt | awk -F", " '{for(i=1;i<=NF;i=i+1) print $i}' | tr -d "'"
```
4.查看链接最多的ip地址
```
netstat -ntu | grep :80 | awk '{print $5}' | cut -d: -f1 | awk '{++ip[$1]} END {for(i in ip) print ip[i],"\t",i}' | sort -nr
```
