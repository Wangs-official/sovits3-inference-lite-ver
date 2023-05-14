# SO-VITS-SVC(3.0) 推理一键包

## 前言

首先，您不得用Sovits推理违法违规的内容，产生的一切问题与一键包制作者和Sovits作者无关

Wangs的BiliBili:[点击进入](https://space.bilibili.com/2128949940)

建议同视频一起食用

有bug欢迎反馈！

## 第一步 下载hubert

精简所需，没带hubert文件，自行下载

```shell
wget -P hubert/ https://github.com/bshall/hubert/releases/download/v0.1/hubert-soft-0d54a1f4.pt
```

## 第二步 将干声文件放入raw文件夹

放进去的必须是干声，无混响无和声的那种

## 第三步 创建环境

防止软件包冲突，我们需要先创建一个conda环境

打开conda命令窗口 输入

```shell
conda create -n sovits python=3.8 -y
```

请自行更新conda源和pip源，百度就能找到 最好用阿里源 然后安装依赖库

```shell
pip3 install -r requirements.txt
```

有些库可能运行时才会发现没有安装，像这样
```
ModuleNotFoundError: No module named xxx
```

请这样安装库 (xxx是缺失的库名)

```shell
pip3 install xxx
```

## 第四步 开始使用

激活Conda环境

```shell
conda activate sovits
```

随后转到该目录下，执行 `python inference.py`

### Part1 下载Hubert文件

如果需要，请输入"1"，会自动下载到hubert文件夹内

### Part2 加载模型文件

有文件后缀名检测以及文件存在检测，模型请导入Sovits3.0的模型，4.0推理不出来声音，后缀名为pth

### Part3 推理前准备

#### Part3.1 多wav文件

请将所有wav文件放到raw文件夹内，输入时使用空格隔开 无需输入文件扩展名

例如:raw文件夹下有 w1.wav w2.wav

那么就输入:`w1 w2`

#### Part3.2 音高偏差

不知道为什么不能输入负号，正常输入就可以，0为默认值

#### Part3.3 多说话人

输入时使用空格隔开

例如:模型内有以下说话人 s1 s2

那么就输入:`s1 s2`

#### slice_db设置

嘈杂的音频可以-30，干声保留呼吸可以-50 , 无需调整请输入-40

输入数字即可

### 开始推理

当你看到`[···]正在推理`字样时，恭喜，一切设置正常，可以正常使用和推理了

推理出的音频在 results 文件夹内

## 全部完成 Enjoyit！（本项目持续更新）
