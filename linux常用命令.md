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
5.awk进行多项排序
```
awk -F'\t' ' $4==3{x=($1%1000<500?5:3)"\t" $6 "\t" ($5==1.0);s[x]++}END{for(i in s)print i,s[i]}' task-4939907-stdout   | sort
```
6.合并相同的字段
awk '{for(i=2;i<=NF;i++)a[$1]=a[$1]","$i}END{for(i in a)print i,a[i]}'

7.输出转换成json格式 | python -m json.tool

systemctl这个命令很强大
