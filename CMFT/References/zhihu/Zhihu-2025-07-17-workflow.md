# 物理学习科研工作流分享
今天突然心血来潮，写篇文章分享一下我的物理学习科研工作流，重在交流，也希望能获得好的建议o(*￣▽￣*)ブ
设备：电脑、ipad和手机。电脑是主阵地，用来运行各种软件以及浏览网页，ipad用来记一些手写笔记，手机用来 ~~刷知乎找乐子~~ 了解最新最好的科研咨询。
我学习科研的workflow主要包括看文献、做实验、看书学理论以及写文章做汇报，下面依次讲讲。
## 看文献
通过看文献能够及时地了解领域的热点，并且有助于产生新的ideas，所以看文献还是很重要的。除了老师发的文章之外，打开各大期刊的官网查看文章还是很重要的，我收藏了[Nature](https://www.nature.com/)、[Science](https://www.science.org/)以及各大子刊，还有[Physical Review Letters](https://journals.aps.org/prl/)，做实验做累了就看看（
如果我认为文章很好，需要仔细阅读文章的时候，我会下载到电脑并且在本地阅读器上看，我使用的是Zotero进行阅读。Zotero用着很舒服，一方面，Zotero是一款专门为科研定制的阅读器，比如可以用doi获取文章条目以及pdf等；另一方面，Zotero还有丰富的插件生态，包括非常好用的翻译插件和参考文献管理系统。具体可以参考Zotero的官网[Zotero | Your personal research assistant](https://www.zotero.org/)。
## 做实验
做实验的时候大部分时间都在刷知乎（
不过做完实验还有处理实验数据，这个时候我有两套方案：我自己画图的时候，一般用Python，Numpy，Scipy和Matplotlib一起用，能实现很强大的处理数据和做图功能；但如果我和另一个人合作，如果对方不用Python，我们一般都会一起使用Origin。
Python和Origin处理数据各自的优缺点都很明显，Python的优势就是可以复用代码并且可以处理大量文件，如果类似的数据很多的话，甚至可以写个包，处理数据的时候调用很方便，Python的劣势应该是对于格式要求很高的图的话，调画图参数会很麻烦。Origin的优势是操作简单，调格式的过程不能说很简单，但至少比较直白，Origin的劣势自然就是比较低效，数据量大的时候处理数据要花很久，当然据说Origin也可以支持Python代码，我也不太了解（
## 看书学习
我感觉自己做实验做多了容易目光呆滞，于是有时候还是得学点东西，这个时候我就会找点书进修一下 ~~（当然大多是时候也看不懂）~~ 这个时候我觉得平板是个很好的选择，相当于草稿纸，可以自己动手算点东西加深印象，ipad+网盘同步也能备份笔记到电脑上，很方便。例如关于网盘同步，挂个goodnotes官网的说明[Use Auto Backup to automatically create a copy of your documents in a supported cloud storage – Goodnotes Support](https://support.goodnotes.com/hc/en-us/articles/360001282956-Use-Auto-Backup-to-automatically-create-a-copy-of-your-documents-in-a-supported-cloud-storage)。
## 写文章做汇报
写文章，分随便场合与正式场合，随便写写我通常用markdown，我目前用的编辑器是obsidian，确实很好用，免费而且简介，插件生态听说很丰富，我还在摸索之中，以前我用VScode写markdown，也很舒服。正式场合，一般而言我倾向于用LaTeX，特别是公式很多的情形，当然如果模板只有word，也只好硬着头皮写，但是word写公式真是太痛苦了。这个网站[Temml - Convert TeX to MathML](https://temml.org/)可以把TeX公式格式转成word公式，也许可以略微减小痛苦。
做汇报，有时候我会用beamer，但更多时候还是得用PPT。beamer确实比较难用，而且做PPT的时候也并非要很多公式，我觉得太多公式会增加理解的难度。当然偶尔我会看到数学系用beamer做的全是公式的presentation，心里就会涌现出极大的敬畏。
## 编程编辑器
Python和LaTeX我都用VScode做编辑器，我从起初到现在一直用VScode，体验很不错就一直也没换。折腾起来不算太麻烦，更重要的是插件生态确实很好用。挂个VScode配置Python和TEX的教程[Getting Started with Python in VS Code](https://code.visualstudio.com/docs/python/python-tutorial)、[LaTeX Workshop - Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=James-Yu.latex-workshop)。
## AI in work
AI现在已经成为一个离不开的工具了，我觉得正确地使用AI至少对我的工作以下几点帮助：
- 当搜索引擎用，忘事的时候就打开AI搜一下，比搜索引擎好的是可以追问
- 提供一些解决问题的思路，问题想不明白就问问AI，说不定在AI的精妙回答（胡言乱语）中就能发现点思路
- 编写代码，这个太有用了，代码可谓AI原生语言，AI写的比我写的好看流畅一万倍
- 图片转公式，这是个妙用，现在AI都可以附件，截个图让AI转成TEX代码，比手敲快很多

以上就是我的学习科研工作流，在此不惭分享，希望各位斧正。也祝各位科研顺利，paper多多😊