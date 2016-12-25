##### 解压rar目录中的所有rar文件 不保持路径 强制覆盖
```bash
find ../rar -name "*.rar" |  xargs -n1 -i unrar e  -o+  "{}"
 ```
 ##### 修复目录中的视频ffmpeg
 ```bash
 find ../avi -name "*.avi" |  xargs -n1 -i echo ' ffmpeg -i "{}" -codec copy `basename "{}"`' >ff.sh && sh ff.sh 
  ```
 ##### debian 下的中文zip解包
 ```bash
sudo apt-get install p7zip-full convmv
 find . -name "*.zip" |  xargs -n1 -i echo  "LANG=C  7za x \"{}\" -y" >conv.sh | sh conv.sh
convmv -f GBK -t utf8 --notest -r . 
 ```
  