
# ![媒体中心](https://github.com/PanZK/MyFiles/raw/master/MediaCenter/MediaCenterCover.png#pic_center "媒体中心示意图")</br></br></br>MediaCenter 家庭媒体中心

随着下载的电影电视剧越来越多，**量变引起质变**，简单的文件夹管理方式越来越痛苦，遂开始研究如何系统性管理大量媒体文件。

为防止各种问题需要重建，并提供交流用，遂记录之，以供参考。

本套媒体中心采用 [Kodi](#11-%E6%92%AD%E6%94%BE%E5%99%A8-kodi "Kodi说明") + [Plex](#12-%E5%AA%92%E4%BD%93%E7%AE%A1%E7%90%86%E7%B3%BB%E7%BB%9F-plex-media-serverplex "Plex说明") + [tinyMediaManager(TMM)](#13-%E5%88%AE%E5%89%8A%E5%99%A8-tinymediamanagertmm "tinyMediaManager(TMM)说明")  + [MediaElch](#14-%E5%88%AE%E5%89%8A%E5%99%A8-mediaelch "MediaElch说明") 构成。

## 1. 系统介绍

简单讲解构成本套媒体中心需要的软件有哪些，是什么。

### 1.1 播放器 [Kodi](https://kodi.tv/ "Kodi官网")

Kodi（以前称为XBMC）是一个免费的开源媒体播放器软件应用程序，支持本地媒体、局域网媒体、流媒体、直播平台、IPTV等媒体。Kodi可用于多种操作系统和硬件平台，Linux、Windows、MacOS、Android等平台可使用，兼容于智能电视机和遥控器。</br>
通俗的说Kodi是用更优雅的方式来管理和播放电影视频音乐，界面美观，使用方便。

### 1.2 媒体管理系统 [Plex Media Server(Plex)](https://www.plex.tv/ "Plex官网")

这是一款主打流媒体传输的软件，它可以把你的所有设备的视频、图片、音乐整合到一个资料库中，只要你的手机、电脑处于同一个局域网内，便可以打通界限，无需下载，使这些媒体资料从任意一台设备均可访问，就像在网站上看视频的实时缓存一样。开启穿透的话也可以在外网使用。

### 1.3 刮削器 [tinyMediaManager(TMM)](https://www.tinymediamanager.org "tinyMediaManager官网")

>**解释**</br>若想在以上两款软件管理并显示出良好效果，就需要将对应视频文件的各种信息给软件，那么我们下的电影电视剧等文件的内容信息如何得来呢，就需要**刮削器**这么个东西来生成nfo等信息文件。

tinyMediaManager是用Java / Swing编写的媒体管理工具，也就是一款**刮削器**，能够为Kodi、jellyfin、emby、Plex媒体服务器提供元数据。tinyMediaManager的原理是根据文件的标题到电影资料网站上匹配电影信息，下载电影的资料及图片到本地上，供Kodi、jellyfin、emby、plex等多媒体软件使用。tinyMediaManager兼容MacOS和Linux，Windows。

### 1.4 刮削器 [MediaElch](https://www.kvibes.de/mediaelch/ "MediaElch官网")

MediaElch(媒体管理软件)是一款免费的开源电影、电视剧、音乐会和音乐的媒体管理软件，同时也是针对Kodi的**刮削器**。它生成的nfo文件、海报、缩略图、截图、演员照片将能够直接被Kodi和Plex引用。Mediaelch能够帮助用户管理自己的多媒体库，通过它加载自定义图像的电影。MediaElch兼容MacOS和Linux，Windows。

## 2 软件选用说明

### 2.1 为什么需要两个刮削器

#### 2.1.1 原因1 [Kodi](#11-%E6%92%AD%E6%94%BE%E5%99%A8-kodi "Kodi说明") 和 [Plex](#12-%E5%AA%92%E4%BD%93%E7%AE%A1%E7%90%86%E7%B3%BB%E7%BB%9F-plex-media-serverplex "Plex说明") 都有自带刮削器，为什么还要用别的？

本身 [Kodi](#11-%E6%92%AD%E6%94%BE%E5%99%A8-kodi "Kodi说明") 和 [Plex](#12-%E5%AA%92%E4%BD%93%E7%AE%A1%E7%90%86%E7%B3%BB%E7%BB%9F-plex-media-serverplex "Plex说明") 都是具有扫描媒体信息的功能，但是因为网络原因，这两款软件在刮削的时候异常慢，还总超时或无法链接,无法刮削，导致媒体信息不全。

故若想达到一个完美的电影墙等展示效果，则需要能够自动搜索+手动编辑的刮削器。

#### 2.1.2 原因2 为什么需要 [TMM](#13-%E5%88%AE%E5%89%8A%E5%99%A8-tinymediamanagertmm "tinyMediaManager(TMM)说明") 和 [MediaElch](#14-%E5%88%AE%E5%89%8A%E5%99%A8-mediaelch "MediaElch说明") 两个刮削器？

刚开始找到的 [TMM](#13-%E5%88%AE%E5%89%8A%E5%99%A8-tinymediamanagertmm "tinyMediaManager(TMM)说明") 刮削器在下载使用后，瞬间感觉它是一个非常棒的刮削器。

它能够在各大平台(如媒体信息数据库网站 [TMDB](https://www.themoviedb.org/ "TMDB官网") 、 [IMDb](https://www.imdb.com/ "IMDb官网") )检索文件信息，检索信息全面、编辑信息方便，更重要的是它能够根据你设置的文件夹、文件名格式，将大量媒体文件及其各种附属信息文件重命名并整理好。

>**顺便提一句**</br>国内的媒体信息数据库网站,射手网几年前就停了，[豆瓣](https://www.douban.com/ "豆瓣官网")又把api接口封了，[人人影视](http://www.rrys.tv/ "人人影视 纪念...")又被封停，所以国内基本没有能用的网站了。</br>而国外网站中对中文支持最好的就是[TMDB](https://www.themoviedb.org/ "TMDB官网")了，所以后面在刮削器的设置上，以上国内网站都可以不用考虑。直接设置为[TMDB](https://www.themoviedb.org/ "TMDB官网")就好。</br>同时发现国内有[射手网(伪)](https://assrt.net/ "射手网(伪)搜索站")，不知道有没插件可以支持。

**但是**， [TMM](#13-%E5%88%AE%E5%89%8A%E5%99%A8-tinymediamanagertmm "tinyMediaManager(TMM)说明") 读取视频源文件的编码信息能力太弱，一些文件的音视频编码无法获取；同时该软件在4.0.0版本以后的免费版，在管理媒体数量、刮削总次数分别设置上限，**完整版需要购买许可证才能解锁(按年收费)**。

>不过查资料看 [TMM](#13-%E5%88%AE%E5%89%8A%E5%99%A8-tinymediamanagertmm "tinyMediaManager(TMM)说明") 的3.0.0大版本是没有这个限制的，但奈何没找到安装包，遂放弃。

所以在 <https://www.52pojie.cn/thread-671625-1-1.html> 帖子中找到开源的 [MediaElch](#14-%E5%88%AE%E5%89%8A%E5%99%A8-mediaelch "MediaElch说明") 刮削器解决管理次数和刮削次数限制问题。

**但是**，在使用 [MediaElch](#14-%E5%88%AE%E5%89%8A%E5%99%A8-mediaelch "MediaElch说明") 后发现其没有批量重命名整理功能。

批量重命名整理功能有时很重要，因为文件夹或文件命名有问题的话，可能导致 [Kodi](#11-%E6%92%AD%E6%94%BE%E5%99%A8-kodi "Kodi说明") 和 [Plex](#12-%E5%AA%92%E4%BD%93%E7%AE%A1%E7%90%86%E7%B3%BB%E7%BB%9F-plex-media-serverplex "Plex说明") 无法获取。

**遂**，只能将 [TMM](#13-%E5%88%AE%E5%89%8A%E5%99%A8-tinymediamanagertmm "tinyMediaManager(TMM)说明") 和 [MediaElch](#14-%E5%88%AE%E5%89%8A%E5%99%A8-mediaelch "MediaElch说明") 两款软件共同保留使用了。

### 2.2 [Kodi](#11-%E6%92%AD%E6%94%BE%E5%99%A8-kodi "Kodi说明") 和 [Plex](#12-%E5%AA%92%E4%BD%93%E7%AE%A1%E7%90%86%E7%B3%BB%E7%BB%9F-plex-media-serverplex "Plex说明") 的区别

#### 2.2.1 [Plex](#12-%E5%AA%92%E4%BD%93%E7%AE%A1%E7%90%86%E7%B3%BB%E7%BB%9F-plex-media-serverplex "Plex说明") 的优缺点

##### 2.2.1.1 Plex 优点

- 对播放设备性能要求很低，兼容性好</br>Plex 对移动设备性能几乎没有要求，因为其提供 web 界面，并且能够将视频统一转码后输出，故几乎凡是能打开 web 的所有智能设备，基本都能使用 Plex 。

- 支持远程访问</br>Plex 可以在外网访问

- 云同步及好友共享库功能，尤其适合家庭影音库、异地恋情侣观影异地恋的情侣交流感情的方式本来就不多，想和对方同时欣赏一部电影时，曾经的做法非常傻：打着电话数123同时按下播放键，网络延迟暂且不谈，两个小时的整段时间其实并不容易抽出来，中途只要有一方离开就又会造成时间差异。Plex 可以完美解决这个需求。利用好友共享功能，随意挑选双方资料库中的内容，同步观看并实时保存进度，即使中途暂停，也能随时续播。

- 媒体库整理功能出色</br>标题既然叫「聚合影音中心」，说明 Plex 的长处在于「聚合与整理」。省心的地方在于，你不用为图片、音频、视频各种类型的文件格式发愁，一股脑的全部把它扔进 Plex，想要查阅或欣赏的时候，它已经在那里静候你了。对于图片和音频我要另外说明一下，由于苹果生态下已经具备了 iTunes ，且图片、音频体积相对较小，完全可以保留原尺寸或经由 iCloud 同步到各个设备，所以我主要用 Plex 串流影片。

- 同时拥有服务器端和客户端，是一整套解决方案，而不仅仅是播放器</br>许多主打「串流」的播放器与 Plex 相比，只提供了「选择源文件- 播放」的单一功能，对于源文件的整理、压制、转码统统没有涉及。Plex 的解决方案比较像网络类型中的「星型拓扑结构」，由中央节点承担相对较重的工作任务。

##### 2.2.1.2 Plex 缺点

- 不支持蓝光原盘和ISO
- 配置简单，个性化空间小

#### 2.2.2 [Kodi](#11-%E6%92%AD%E6%94%BE%E5%99%A8-kodi "Kodi说明") 的优缺点

##### 2.2.2.1 Kodi 优点

- 支持蓝光原盘和ISO
- 配置丰富，功能强大(是优点也是缺点)

##### 2.2.2.2 Kodi 缺点

- 配置复杂
- 界面和操作不够美观和流畅（当然各种皮肤能解决部分问题）
- 不能远程播放
- 不同终端需要逐一单独配置
- 播放能力取决于终端机能

#### 2.2.3 总结下

- Plex 首先是个服务器，你把它装在家里的媒体服务器上，然后你所有的设备都可以连接Plex看视频。Plex 会自动把视频重编码后输出到你的手机平板电视机上。

- Kodi 是个客户端，你在你要放视频的设备上装上它，让它索引你的本地和局域网上面的共享视频。 然后他会漂漂亮亮的自动把你的电影电视剧什么的整理好，你要看的时候，你用你的播放设备解码。

- Plex 对播放设备的性能没要求，但是需要个好点的服务器。（同时重编码输出到三四个设备上的话，做好上 Xeon 的准备。）</br>- Kodi 对播放设备的要求稍微高点，但是文件服务器的配置多烂都无所谓。（其实也没多高，树莓派都能跑Kodi）

**总之**</br>
Kodi 适合单身宅，家庭用太麻烦了</br>
Plex 需要比较强劲点的服务器，配置简单

>[知乎：xbmc（kodi）plex 哪个您更中意?](https://www.zhihu.com/question/30096498 "xbmc（kodi） plex  哪个您更中意 ?- 知乎")

### 2.3 如何搭配

以上及款软件已经推荐完毕，那如何根据自己的需要进行部署呢，以下表格给出答案，当然也可以根据自己喜好进行搭配。

|                             需求                             | Kodi | Plex | TMM | MediaElch |              总结             |
|--------------------------------------------------------------|:----:|:----:|:---:|:---------:|-------------------------------|
| 媒体在本地，只在本机或客厅电视播放，不需要系统媒体管理     |   √  |      |     |           | [Kodi](#11-%E6%92%AD%E6%94%BE%E5%99%A8-kodi "Kodi说明")（Kodi自带刮削器）        |
| 媒体在本地，只在本机或客厅电视播放，系统管理媒体文件 |   √  |      |  √  |     √     | [Kodi](#11-%E6%92%AD%E6%94%BE%E5%99%A8-kodi "Kodi说明") + [TMM](#13-%E5%88%AE%E5%89%8A%E5%99%A8-tinymediamanagertmm "tinyMediaManager(TMM)说明") + [MediaElch](#14-%E5%88%AE%E5%89%8A%E5%99%A8-mediaelch "MediaElch说明")        |
| 不想要复杂设置，多设备使用                                   |      |   √  |  √  |           | [Plex](#12-%E5%AA%92%E4%BD%93%E7%AE%A1%E7%90%86%E7%B3%BB%E7%BB%9F-plex-media-serverplex "Plex说明") + [TMM](#13-%E5%88%AE%E5%89%8A%E5%99%A8-tinymediamanagertmm "tinyMediaManager(TMM)说明")                    |
| 系统性管理媒体文件，播放随意                                 |      |   √  |  √  |     √     | [Plex](#12-%E5%AA%92%E4%BD%93%E7%AE%A1%E7%90%86%E7%B3%BB%E7%BB%9F-plex-media-serverplex "Plex说明") + [TMM](#13-%E5%88%AE%E5%89%8A%E5%99%A8-tinymediamanagertmm "tinyMediaManager(TMM)说明") + [MediaElch](#14-%E5%88%AE%E5%89%8A%E5%99%A8-mediaelch "MediaElch说明")        |
| 远程访问，系统性管理媒体文件，良好播放体验                   |   √  |   √  |  √  |     √     | [Kodi](#11-%E6%92%AD%E6%94%BE%E5%99%A8-kodi "Kodi说明") + [Plex](#12-%E5%AA%92%E4%BD%93%E7%AE%A1%E7%90%86%E7%B3%BB%E7%BB%9F-plex-media-serverplex "Plex说明") + [TMM](#13-%E5%88%AE%E5%89%8A%E5%99%A8-tinymediamanagertmm "tinyMediaManager(TMM)说明") + [MediaElch](#14-%E5%88%AE%E5%89%8A%E5%99%A8-mediaelch "MediaElch说明") |

>**有些情况只能使用 [Plex](#12-%E5%AA%92%E4%BD%93%E7%AE%A1%E7%90%86%E7%B3%BB%E7%BB%9F-plex-media-serverplex "Plex说明")**</br>若多设备使用，挨个配置 [Kodi](#11-%E6%92%AD%E6%94%BE%E5%99%A8-kodi "Kodi说明") 会很麻烦</br>若需要外网远程访问则也只能使用 [Plex](#12-%E5%AA%92%E4%BD%93%E7%AE%A1%E7%90%86%E7%B3%BB%E7%BB%9F-plex-media-serverplex "Plex说明")。

## 3. 安装&配置

到了重头戏，安装这些软件踩了无数坑，总结如下。

### 3.1 安装&配置播放器 [Kodi](#11-%E6%92%AD%E6%94%BE%E5%99%A8-kodi "Kodi说明")

#### 3.1.1 安装 [Kodi](#11-%E6%92%AD%E6%94%BE%E5%99%A8-kodi "Kodi说明")

这是[Kodi官网](https://kodi.tv/ "Kodi官网")，这是[Kodi的github页面](https://github.com/xbmc/xbmc "Kodi的github页面")。

进入官网的[下载页面](https://kodi.tv/download "官网下载页面")在下面找到自己的平台下载链接，下载安装包。如图：

![Kodi下载图](https://github.com/PanZK/MyFiles/raw/master/MediaCenter/MediaCenter-Kodi.Download.png#pic_center "Kodi下载图")

除Linux平台外，其他几个平台下载后直接安装即可，Linux需要用[官网文档](https://kodi.wiki/view/HOW-TO:Install_Kodi_for_Linux "官网文档")提示的内容通过命令安装。
如Ubuntu的安装命令如下：

```shell
    sudo apt-get install software-properties-common
    sudo add-apt-repository ppa:team-xbmc/ppa
    sudo apt-get update
    sudo apt-get install kodi
```

#### 3.1.2 配置 [Kodi](#11-%E6%92%AD%E6%94%BE%E5%99%A8-kodi "Kodi说明")

下面转载并整理下[豆瓣博主-没纹身的男孩-一个私人影视库的解决方案——KODI（上）](https://www.douban.com/note/709691715/ "豆瓣-没纹身的男孩-一个私人影视库的解决方案——KODI（上）")的详细说明。

##### 3.1.2.1 Kodi中文设置

安装完成后要做的第一件事就是把语言改成中文，这个设置过程各平台的操作相同，区别只是你用鼠标、遥控器还是手指头，不过新老版本之间选项的所在位置可能存在一定差别。

这里要提一下，国内一些电视和电视盒子厂商的遥控器按键对应与KODI不同，比如返回键在KODI中不好用，那么你可能就需要使用遥控器的删除键或者退格键来实现返回功能。

另外电脑版的鼠标右键点击操作，使用遥控器的话就是中键（OK键）长按，后面可能不再特别说明

电脑版的界面滑动如果发现鼠标操作不方便，请使用键盘上下左右键。

安装完成后运行KODI，主界面如上图所示，点击黄圈里的齿轮图标进入设置界面。

![Kodi中文设置1](https://github.com/PanZK/MyFiles/raw/master/MediaCenter/MediaCenter-Kodi.Lang1.webp#pic_center)

进入设置界面后我们先进入Interface，如下图所示。

![Kodi中文设置2](https://github.com/PanZK/MyFiles/raw/master/MediaCenter/MediaCenter-Kodi.Lang2.webp#pic_center)

然后在Skin菜单中找到Fonts选项。

![Kodi中文设置3](https://github.com/PanZK/MyFiles/raw/master/MediaCenter/MediaCenter-Kodi.Lang3.webp#pic_center)

把Skin default修改为Arial based

![Kodi中文设置4](https://github.com/PanZK/MyFiles/raw/master/MediaCenter/MediaCenter-Kodi.Lang4.webp#pic_center)

然后我们到Skin底下的Regional菜单中找到Language，在Language中选择Chinese(simple)，点击后就开始进行中文版本的安装了，请耐心等待。（此过程需要联网，因为要下载中文语言包）
完成后的设置界面

![Kodi中文设置5](https://github.com/PanZK/MyFiles/raw/master/MediaCenter/MediaCenter-Kodi.Lang5.webp#pic_center)

#### 3.1.2.2 Kodi媒体库资源的扫描

所谓电影库在KODI中统称为资料库，无论是电影还是剧集、音乐、或者照片都叫相应的资料库。下面详细讲一下电影资料库的设置过程。

首先我们回到主界面，在设置界面按ESC（遥控器按返回）就能返回主界面，返回上一级则使用退格键，然后选择电影菜单中的进入文件区。

![Kodi媒体库资源的扫描01](https://github.com/PanZK/MyFiles/raw/master/MediaCenter/MediaCenter-Kodi.Lib01.webp#pic_center)

进入文件区后我们会看到这样的界面，点击“添加视频”。也注意那个移动硬盘(D:)标志，也许后面会用到。

![Kodi媒体库资源的扫描02](https://github.com/PanZK/MyFiles/raw/master/MediaCenter/MediaCenter-Kodi.Lib02.webp#pic_center)

点击添加视频后看到这样的界面，我们点击“浏览“”

![Kodi媒体库资源的扫描03](https://github.com/PanZK/MyFiles/raw/master/MediaCenter/MediaCenter-Kodi.Lib03.webp#pic_center)

从这里开始“世界线”要开始分叉了，因为我使用的是Windows版，而我这台电脑只有1个C盘，所以我选择第一个“C:(Locak Disk)”也就是C盘。

若如你是通过局域网共享文件，那么选择「(SMB)网络」，如果是使用的NAS存储，那么选择「添加网络位置」。

>**注：**</br>- 在这里要选择到自己保存视频文件的上一级文件夹即可</br>- 建议将每部电影单独保存在相应的文件夹内，方便后续添加视频源文件和刮削操作</br>- 若媒体文件分散在多个目录，那么只需多次分别添加目录即可</br>- 本人为Ubuntu系统，操作一致

使用电视连接U盘或者移动硬盘的同学如果在这里没找到你的移动存储设备，可能要右键点击前页面我提到的移动硬盘(D:)或者U盘，然后点击设置内容。

![Kodi媒体库资源的扫描04](https://github.com/PanZK/MyFiles/raw/master/MediaCenter/MediaCenter-Kodi.Lib04.webp#pic_center)

点击C盘后，可以看到我有一个叫“3-9电影”文件夹，而你要选择的则是你装电影的那个文件夹，所有电影一股脑全放一个文件夹也完全没问题。

![Kodi媒体库资源的扫描05](https://github.com/PanZK/MyFiles/raw/master/MediaCenter/MediaCenter-Kodi.Lib05.webp#pic_center)

在我的电脑里看这个“3-9电影”文件夹是这个样子的，可以像我这每个电影再单独建立一个文件夹目录，也可以是MP4、MKV等文件直接放进来，但更推荐我使用的这种方式，这样可以让字幕文件和未来的影片信息文件存放更有序。此外ISO蓝光原盘格式也是可以直接放进来的。

![Kodi媒体库资源的扫描06](https://github.com/PanZK/MyFiles/raw/master/MediaCenter/MediaCenter-Kodi.Lib06.webp#pic_center)

选择了“3-9电影文件夹后”会进入目录里面，然后我们不要选择任何具体的电影，直接点右边的确定按键，就来到下面的页面。

![Kodi媒体库资源的扫描07](https://github.com/PanZK/MyFiles/raw/master/MediaCenter/MediaCenter-Kodi.Lib07.webp#pic_center)

上面是电影文件夹的路径，在下面你可以为这个电影库起个你喜欢的名字，这里改名的话涉及一个输入法的问题之前忘了讲：请到界面设置的区域里面，有个键盘布局选项，添加一个叫“Chinese BaiduPY”的输入法，这样在虚拟键盘中就可以选择它输入中文了。

电脑版似乎也只能用虚拟键盘输入，不太方便。

![Kodi媒体库资源的扫描08](https://github.com/PanZK/MyFiles/raw/master/MediaCenter/MediaCenter-Kodi.Lib08.webp#pic_center)

然后点击此目录包含的内容，选择“电影”，选择完界面会变成下面的样子

![Kodi媒体库资源的扫描09](https://github.com/PanZK/MyFiles/raw/master/MediaCenter/MediaCenter-Kodi.Lib09.webp#pic_center)

“信息提供者”我们使用默认的 The Movie Database，不需要更改。然后记得打开“电影在以片名命名的单独目录中”这个选项，之前推荐每个电影单独建一个文件夹目录。

![Kodi媒体库资源的扫描10](https://github.com/PanZK/MyFiles/raw/master/MediaCenter/MediaCenter-Kodi.Lib10.webp#pic_center)

设置界面主要设置首选语言，点击后选择倒数第二个zh-cn。这样最后你电影库的电影名称和相关信息都将是中文的，如果喜欢英文的话这里就保留默认的en。

点击了两次确定后，询问我们是否刷新目录下所有项目的信息，毫不犹豫的选择“是”

![Kodi媒体库资源的扫描11](https://github.com/PanZK/MyFiles/raw/master/MediaCenter/MediaCenter-Kodi.Lib11.webp#pic_center)

然后可以看到这里多了一个我们命名的“电影”，右上角则开始扫描电影信息。

![Kodi媒体库资源的扫描12](https://github.com/PanZK/MyFiles/raw/master/MediaCenter/MediaCenter-Kodi.Lib12.webp#pic_center)

如果你电影很多，扫描会需要一定时间。如果扫描过程中一直提示远程连接有问题，可能是墙内网络连接TMDB数据库不稳定，请耐心的一直点确定。另外建议在进行这些设置之前，规范一下你的电影命名，文件名最前面是电影标准的中文名或英文名比较好，这样能大大提高扫描准确率，减少后期的修改。

>**注：**</br>- 这一步就体现出刮削器的重要性了，Kodi本身是可以能够刮削的，但会有网络不好无法下载、识别率低下各种问题</br>- 等后面安装好其他刮削器后，这里设置会稍有变动</br>- 文件夹和文件的命名结构良好能够提高刮削效率，建议改成“中文片名.英文片名.年份.视频编码.音频编码.扩展名”方式命名，每个字段之间以 “.” 间隔

扫描完成后我们返回主界面，鼠标放到电影菜单上就是下面这个样子啦。

![Kodi封面图](https://github.com/PanZK/MyFiles/raw/master/MediaCenter/MediaCenter-Kodi.Cover.webp#pic_center)

>后面更细致操作可以转到原博文学习：[豆瓣博主-没纹身的男孩-一个私人影视库的解决方案——KODI（上）](https://www.douban.com/note/709691715/ "豆瓣-没纹身的男孩-一个私人影视库的解决方案——KODI（上）")。

以添加电影为例，Kodi媒体库资源的扫描讲到这，添加剧集或其他媒体库操作基本类似。

只提一下剧集目录和命名问题，其余不做赘述。

>同一个剧集应放在一个文件夹里，如果一个剧集有很多季，则最好每一个季再用一个文件夹装起来，并且在每一季的文件夹的命名中加入”S01“，”S02“做区分。每一集的视频文件的文件名中要有S01E02（第一季第二集）这样的识别符

#### 3.1.2.3 修改Kodi的默认播放器

虽然Kodi的播放器很不错，但是我在Ubuntu的本机MPV播放器里做好了更多习惯的配置，遂准备将默认播放器改一下。

kodi设置外置播放器很容易，只要在 [Kodi 用户数据配置路径](http://www.kodiplayer.cn/course/2947.html "Kodi用户数据配置文件在哪？配置文件详细介绍")下，新建一个 [playercorefactory.xml](Kodi/playercorefactory.xml "我所使用的playercorefactory.xml") 就行了。

各系统的Kodi用户数据配置路径如下：

| 系统        | 路径                                                                               |
|-------------|------------------------------------------------------------------------------------|
| Windows     | C:\Users\<your username>\AppData\Roaming\Kodi\userdata                             |
| Linux       | ~/.kodi/userdata/                                                                  |
| MacOS       | /Users/<your_user_name>/Library/Application Support/Kodi/userdata/                 |
| iOS         | /private/var/mobile/Library/Preferences/Kodi/userdata/                             |
| Android     | Android/data/org.xbmc.kodi/files/.kodi/userdata/                                   |
| LibreELEC   | /storage/.kodi/userdata/                                                           |
| OSMC        | /home/osmc/.kodi/userdata/                                                         |
| Windows UWP | %LOCALAPPDATA%\Packages\XBMCFoundation.Kodi_4n2hpmxwrvr6p\LocalCache\Roaming\Kodi\ |

[点击下载](https://raw.githubusercontent.com/PanZK/Record_InstallSoftware/main/MediaCenter/Kodi/playercorefactory.xml "我所使用的playercorefactory.xml")我配置的playercorefactory.xml。

简单解释下xml中的参数：

\<player>标签当中的"name"参数表示播放器名称，引号内自己命名
audio和video参数表示该播放器对哪种媒体适用，适用就用"true"，不适用就用"false"，如：

```xml
<player name="MPV" type="ExternalPlayer" audio="false" video="true">    #表示MPV只对视频媒体生效
    ##配置信息
</player>
```

\<filename>标签内需要填写播放器路径，如：

```xml
<filename>/usr/bin/mpv</filename>   #表示Linux中mpv的路径
<filename>C:/Program Files (x86)/DAUM/PotPlayer/PotPlayerMini.exe</filename>    #表示Windows中PotPlayer的路径
```

\<hidexbmc>标签表示打开该播放器后Kodi是否隐藏界面，隐藏就用"true"，不隐藏就用"false"，如：

```xml
<hidexbmc>false</hidexbmc>   #表示保留Kodi界面
```

当然如此操作也有一定的缺点

- 无法记忆播放记录</br>用外置播放器使得Kodi无法记录关闭视频时的位置，这点好在我将MPV设置了记忆记录
- 字幕文件无法加载</br>建议多下载压制好的视频文件

那如何修改成Kodi原生播放器？

- 临时换回原生播放器</br>每次播放时，在打开方式里选择Videoplayer
- 永久换回原生播放器</br>直接删除playercorefactory.xml文件

#### 3.1.2.4 Kodi的其他设置

- 修改Kodi的主题皮肤
- 常用快捷键
- [在 Kodi 里安装 Plex 插件](#3224-%E5%9C%A8-kodi-%E9%87%8C%E5%AE%89%E8%A3%85-plex-%E6%8F%92%E4%BB%B6 "在 Kodi 里安装 Plex 插件")
- 将手机设置成Kodi的遥控器
- 将Kodi设置DLNA，其他智能设备的媒体可以推送过来播放
- 设置IPTV源，看电视直播
- 安装各种Kodi插件
- 观看网络平台直播

>**相关参考链接**</br>- [我是怎样用这个神器管理我的4T电影的-马小帅的文章-知乎](https://zhuanlan.zhihu.com/p/84017222 "我是怎样用这个神器管理我的4T电影的 - 马小帅的文章 - 知乎")</br>- [Kodi 以更优雅的方式来管理你的电影](https://www.jianshu.com/p/4e74063fed8a "Kodi 以更优雅的方式来管理你的电影")</br>- [手把手教你用Kodi，搭建最强私人「娱乐/学习」中心！（小白篇）](https://post.m.smzdm.com/p/ammqnld4/ "手把手教你用Kodi，搭建最强私人「娱乐/学习」中心！（小白篇）")</br>- [2021年最新直播源](http://www.kodiplayer.cn/movie/2898.html "Kodi IPTV直播源m3u8下载 2021年最新直播源")</br>- [利用树莓派和Kodi投屏](https://blog.csdn.net/biocity/article/details/85597058 "CSDN-利用树莓派和Kodi投屏")</br>- [HOW TO - Launch MPC-HC/MPC-BE with madVR as an External Player](https://forum.kodi.tv/showthread.php?tid=209596 "HOW TO - Launch MPC-HC/MPC-BE with madVR as an External Player")

### 3.2 安装&配置媒体管理系统 [Plex](#12-%E5%AA%92%E4%BD%93%E7%AE%A1%E7%90%86%E7%B3%BB%E7%BB%9F-plex-media-serverplex "Plex说明")

#### 3.2.1 安装 [Plex](#12-%E5%AA%92%E4%BD%93%E7%AE%A1%E7%90%86%E7%B3%BB%E7%BB%9F-plex-media-serverplex "Plex说明")

这是 [Plex官网](https://www.plex.tv/ "Plex官网")，这是 [Plex中文官网](https://www.plex.tv/zh/ "Plex中文官网")

##### 3.2.1.1 注册 Plex 用户

点击进入 [Plex官网](https://www.plex.tv/ "Plex官网") 后先注册 Plex 账户。

有了 Plex 账户后可以将信息管理更细致化，并且能够远程控制。当然，不注册 Plex 账户也**无法使用** Plex。

##### 3.2.1.2 安装 Plex 服务端

Plex 分为服务端和应用端，应用端无非就是在设备上的播放器而以，也有很多应用可以代替，下面主讲服务端。

点击 [Plex下载页](https://www.plex.tv/zh/media-server-downloads/ "Plex下载页") 选择对应平台的Plex安装包下载。

![Plex下载](https://github.com/PanZK/MyFiles/raw/master/MediaCenter/MediaCenter-Plex.Download.png#pic_center)

下载好后进入下载目录执行以下命令进行安装。

```shell
    dpkg -i plexmediaserver_1.21.3.4046-3c1c83ba4_amd64.deb
    #安装包命名规则为plexmediaserver_<版本号>-<版本号>_<架构>.deb
```

#### 3.2.2 配置 [Plex](#12-%E5%AA%92%E4%BD%93%E7%AE%A1%E7%90%86%E7%B3%BB%E7%BB%9F-plex-media-serverplex "Plex说明")

##### 3.2.2.1 Plex 服务端基本命令

```shell
    service plexmediaserver status
    #检查 plexmediaserver 服务状态，若提示信息为active(running)则为安装成功，服务已经运行。

    service plexmediaserver restart
    #重启 plexmediaserver 服务

    service plexmediaserver stop
    #停止 plexmediaserver 服务
```

设置 Plex Media Server 开机自启动:

```shell
    sudo systemctl enable plexmediaserver.service
    sudo systemctl start plexmediaserver.service
```

##### 3.2.2.2 Plex web管理

Plex 提供web管理界面，默认32400端口。

在本地网络主机中打开web浏览器，输入输入以下地址进入 Plex 管理界面，并完成以下步骤来配置Plex。

```html
    http://YourIP:32400/web
    http://localhost:32400/web
```

在登陆界面输入前面注册的 Plex 账户和密码，登陆本机的 Plex Media Server。

后面 Plex 会引导你一步一部进行媒体库添加，第一次设置不好没关系，引导教程过后这些设置都是可以再更改的。

因 Plex 直接可用中文界面，故不赘述。

##### 3.2.2.3 Plex 加载本地 nfo 文件插件

Plex 默认从网上刮削电影信息，但同样因各种原因必然失败，所以需要让 Plex 从本地加载刮削器生成的 nfo 视频信息文件。

>用刮削器后 Kodi 也可以直接读取本地 nfo 视频信息文件，从而免去很多麻烦。

这里提供两个插件[XBMCnfoMoviesImporter.bundle-for-Plex](https://github.com/gboudreau/XBMCnfoMoviesImporter.bundle "XBMCnfoMoviesImporter.bundle-for-Plex") 和 [XBMCnfoTVImporter.bundle-for-Plex](https://github.com/gboudreau/XBMCnfoTVImporter.bundle "XBMCnfoTVImporter.bundle-for-Plex") 。

这里也有网友整理好的：[BD云链接](https://pan.baidu.com/s/1GT9yC18LCOxUBlmI3IpkfA "BD云链接") 和提取码：x9xy，可以直接下载。

下载后分别解压出两个文件夹，解压出的文件夹名带有_-master_字样，故分别将其重命名为_XBMCnfoMoviesImporter.bundle_和_XBMCnfoTVImporter.bundle_。

>可以分别进入这两个目录，查看里面是分别否存在_Contents_目录，若存在则文件结构正确。

然后将_XBMCnfoMoviesImporter.bundle_和_XBMCnfoTVImporter.bundle_两个目录将放到 PLEX 插件目录下

```shell
    /var/lib/plexmediaserver/Library/Application Support/Plex Media Server/Plug-ins
    #Linux路径

    *\Plex\Library\Application SupportPlex\Media Server\Plug-ins
    #Windows路径

    appdata/plex/Library/Application SupportPlex/Media/ServerPlug-ins
    #UNraid路径
```

重启 Plex。

进入 Plex 页面，选择电影 -> 找到资料库 -> 管理资料库 -> 编辑...

![Plex本地信息插件图1](https://github.com/PanZK/MyFiles/raw/master/MediaCenter/MediaCenter-Plex.Importer1.png#pic_center)

在高级的选项，代理 选择我们刚刚放入插件的代理工具：

![Plex本地信息插件图2](https://github.com/PanZK/MyFiles/raw/master/MediaCenter/MediaCenter-Plex.Importer2.png#pic_center)

这样就能加载本地视频信息了。

值得注意的地方，在这个代理插件设置最下面的地方，把这个勾勾去掉。大意是生成很多标签分组，会很乱，必须去掉这个勾勾：

![Plex本地信息插件图3](https://github.com/PanZK/MyFiles/raw/master/MediaCenter/MediaCenter-Plex.Importer3.png#pic_center)

刷新所有元数据，Plex就能加载到本地的 nfo 文件和封面图了。

同理剧集也是同样的操作，只不过剧集选项中没有上面的那个勾勾，改成用插件后就不需要特别关闭那个勾勾了。

##### 3.2.2.4 在 Kodi 里安装 Plex 插件

前面已经讲过安装 Kodi ，而在 Kodi 里有 Plex 的插件，可以直接在 Kodi 里播放 Plex 的内容。

为什么推荐在Kodi里安装Plex插件？

因为Plex播放视频需解码或者转码，占用Plex服务器端资源；

一些不支持的视频编码，使用Plex客户端无法解码播放；

Plex客户端收费……

在Kodi里安装Plex插件能解决以上问题，功能界面与Plex客户端没差别。

Kodi 中文网[这篇文章](http://www.kodiplayer.cn/plugins/2918.html "这篇文章")有介绍，这里不再赘述。

##### 3.2.2.4待补充更多 Plex 配置

Plex 更多设置后续补充

>**相关参考链接**</br>- [Plex: 为你的所有设备打造一个聚合影音中心](https://sspai.com/post/45414 "Plex: 为你的所有设备打造一个聚合影音中心")</br>- [Plex完美个人影音云盘搭建教程-Plex Media Server安装与使用方法](https://www.freehao123.com/plex-plex-media-server/ "Plex完美个人影音云盘搭建教程-Plex Media Server安装与使用方法")</br>- [【应用教程】Plex使用指南（一）](http://www.360doc.com/content/19/0219/14/60482440_816092287.shtml "【应用教程】Plex使用指南（一）")</br>- [使用PLEX必看：加载本地nfo文件插件，配合tmm刮削工具的最佳方法，打造个人家庭影院服务器](https://post.smzdm.com/p/ar0v98m7/ "使用PLEX必看：加载本地nfo文件插件，配合tmm刮削工具的最佳方法，打造个人家庭影院服务器")</br>- [如何安装家庭媒体中心 Plex Media Server](https://linux.cn/article-5932-1.html "如何安装家庭媒体中心 Plex Media Server ")</br>- [一步一步，轻松从无到有，搞定自己的NAS媒体服务器](https://koolshare.cn/thread-148522-1-1.html "一步一步，轻松从无到有，搞定自己的NAS媒体服务器")</br>- [小白瞎折腾 篇十四：玩转群晖NAS，影音篇（二）：本地、远程我都行，影音平台中全面性选手——PLEX](https://www.sohu.com/a/313724718_100298843 "小白瞎折腾 篇十四：玩转群晖NAS，影音篇（二）：本地、远程我都行，影音平台中全面性选手——PLEX")</br>- [PLEX，目前最佳的IPTV直播软件，没有之一](https://koolshare.cn/thread-148522-1-1.html "PLEX，目前最佳的IPTV直播软件，没有之一")

### 3.3 安装&配置刮削器 [tinyMediaManager(TMM)](#13-%E5%88%AE%E5%89%8A%E5%99%A8-tinymediamanagertmm "tinyMediaManager(TMM)说明")

#### 3.3.1 安装 [tinyMediaManager(TMM)](#13-%E5%88%AE%E5%89%8A%E5%99%A8-tinymediamanagertmm "tinyMediaManager(TMM)说明")

[tinyMediaManager官网](https://www.tinymediamanager.org "tinyMediaManager官网")

#### 3.3.2 配置 [tinyMediaManager(TMM)](#13-%E5%88%AE%E5%89%8A%E5%99%A8-tinymediamanagertmm "tinyMediaManager(TMM)说明")

### 3.4 安装&配置刮削器 [MediaElch](#14-%E5%88%AE%E5%89%8A%E5%99%A8-mediaelch "MediaElch说明")

#### 3.4.1 安装 [MediaElch](#14-%E5%88%AE%E5%89%8A%E5%99%A8-mediaelch "MediaElch说明")

[MediaElch官网](https://www.kvibes.de/mediaelch/ "MediaElch官网")

#### 3.4.2 配置 [MediaElch](#14-%E5%88%AE%E5%89%8A%E5%99%A8-mediaelch "MediaElch说明")

```python
aaa
```

[]( "")
