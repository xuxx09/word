### 生成tags索引
sudo ctags -R *

### 配置~/.vimrc文件
set tags=tags
set autochdir

### 查找字符串在文件出现位置
grep -Rn UDPTransceiver
