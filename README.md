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
- 只需一条命令，简单快捷
- 选项丰富，满足更多场景
- 支持人性化的选项输入交互

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

## 选项使用

```sh
# 使用人性化的选项输入交互
flv2mp4 -q

# 持续检查需要转换的文件
flv2mp4 -w

# 是否自动归档（暂支持按日期归档）
flv2mp4 -a

# 转换完成后，删除flv源文件
flv2mp4 -r

# 指定输入输出的工作目录，支持相对（可以是相对目录）
flv2mp4 -c "./flvInputDir" -o "./mp4OutputDir"

# 组合使用（持续检查需要转换的文件，转换完后按日期自动归档，且删除掉转换成功的flv源文件）
flv2mp4 -war -c "./flvInputDir" -o "./mp4OutputDir"

# 使用帮助
flv2mp4 -h
```

## 选项帮助

```sh
flv2mp4 -h

# 输出如下帮助信息：

Usage: flvToMp4 [options]
Options:
  -V, --version         output the version number
  -d, --debug           是否输出相关调试信息 (default: false)
  -q, --inquirer        是否使用inquirer来引导输入相关参数 (default: false)
  -w, --watch           是否持续检查有需要转换的文件 (default: false)
  -t, --timeout <type>  指定重复执行转换检查的时间间隔，默认30秒 (default: 30)
  -a, --archive         是否自动归档（暂支持按日期归档） (default: false)
  -r, --remove          转换完成后，是否删除flv源文件 (default: false)
  --no-skip             是否自动跳过不符合转换条件的文件
  -c, --cwd <type>      指定命令行的工作目录
  -o, --output <type>   指定转换成功后的输出目录
  -h, --help            display help for command
```

## 本地调试

将当前项目安装到全局

```sh
npm i . -g
```
