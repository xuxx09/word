1. 查看进程信息
```
ps -aux
```
2. awk跳过空白行后进行排序
```
cat text.txt| awk '{if(length($0)>0) print $0}' | sort -k2
```
