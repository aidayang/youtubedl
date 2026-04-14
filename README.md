# youtubedl
### 从youtube下载1080P视频方法

有时候需要从youtube下载视频素材，以前都是用的专门的下载网站下的，现在很多网站都不能直接下载了如cobalt.tools，所以只能用yt-dlp，这里记录下用yt-dlp下载youtube视频的方法，方便以后查看

本教程编写时间2026年4月14日，下面操作步骤可能存在时效性，因为google相关服务会有变动，本方法未来可能无效

首先安装yt-dlp，没安装Python的话还得先安装Python

pip install yt-dlp

安装nodejs

https://nodejs.org/zh-cn/download

安装Chrome浏览器插件用于提取cookies

https://chromewebstore.google.com/detail/get-cookiestxt-locally/cclelndahbckbenkjhflpdbgdldlbecc

打开youtube.com导出你的cookies保存到本地电脑上，例如，我把cookies保存到电脑桌面命名为yt.txt，路径为C:\Users\Administrator\Desktop\yt.txt

然后运行下面命令下载youtube带声音的1080P视频，以视频https://www.youtube.com/watch?v=X7L7-ZSk5Lo为例

yt-dlp -f "bestvideo[height=1080]+bestaudio" --merge-output-format mp4 --remote-components ejs:github --cookies C:\Users\Administrator\Desktop\yt.txt https://www.youtube.com/watch?v=X7L7-ZSk5Lo

如果你上面命令无法正常下载视频，可能是环境配置有问题。我电脑没装Python，在虚拟环境里运行的，且手动指定nodejs路径，我是通过下面命令下载的，你可以参考一下。

python -m yt_dlp -f "bestvideo[height=1080]+bestaudio" --merge-output-format mp4 --js-runtimes node:"E:\nodejs\node.exe" --remote-components ejs:github --cookies C:\Users\Administrator\Desktop\yt.txt https://www.youtube.com/watch?v=X7L7-ZSk5Lo



考虑到未来可能仍然无法使用类似cobalt.tools的网站直接下载，还是得在本地手动操作，有时间有必要的话我就做个整合包版，简化操作步骤，毕竟我操作起来也嫌麻烦😂
