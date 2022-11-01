# flv2mp4

> 基于ffmpeg的批量flv快速转换成mp4文件的脚本

## 使用说明

使用前先确保你电脑已经安装了：[ffmpeg](http://ffmpeg.org/)  

基本工作原理为执行ffmpeg的以下命令：

```sh
ffmpeg -i input.flv -vcodec copy -acodec copy output.mp4
```

## 特性

- 支持批量转换
- 不重新编码，快速转换
- 自动检测是否存在flv文件
- 自动跳过已转换完成的文件
- 可随时终止，无需担心出错
- 只有一条命令，简单快捷

### 安装脚本

```sh
# npm
npm install flv2mp4 --global

# yarn

yarn global add flv2mp4
```

中国大陆用户可使用阿里源进行加速安装

```sh
# npm
npm install flv2mp4 --global --registry=https://registry.npmmirror.com

# yarn

yarn global add flv2mp4 --registry=https://registry.npmmirror.com
```

### 使用脚本

去到存在flv文件的目录，直接运行以下命令

```sh
flv2mp4
```

## 本地调试

将当前项目安装到全局

```sh
npm i . -g
```
