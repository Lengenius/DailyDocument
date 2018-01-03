####Scrapy 安装
如果你之前按照我的方案[《小说python开发环境配置》][1]配置好了Pyenv + pyenv-virtualenv + sublime 的配置环境的话，那么就可以直接按照下面的步骤进行了。

首先我们新建一个虚拟环境(virtual environment):

```
pyenv virtualenv 3.5.3 spider
```
这个虚拟环境的名字就叫做spider了，配置的是python 3.5.3 的版本，你也可以根据需求选择其他的版本或者你喜欢的名字。

然后激活这个虚拟环境:

```
pyenv activate spider

```
不出意外的话，你的提示符前面会增加`(spider)`的字样，如图所示。这就是说你已经进入到spider 这个虚拟环境当中了。
接下来你就拥有了一个独立的虚拟环境，你可以“随意的”安装任意插件，自由飞翔了。

输入:

```
pip install scrapy
```
就会自动安装好Scrapy了。pip 是一个python自带的包管理工具，2.7之后的python版本都自动安装了，我们的虚拟环境中自然也是有的。到这里就完成了第一步Scrapy 的安装。是不是跃跃欲试想要开始下一步呢？跟我来吧

#####运行Scrapy 示例程序
运行示例程序的主要目的呢，就是检测一下我们的环境配置有没有问题。你也可以去Scrapy 的[官方文档][2]看看。作为程序员，一定要常看文档才行啊。
官网给出的文档如下:

```python
import scrapy

class QuotesSpider(scrapy.Spider):
    name = "quotes"
    start_urls = [
        'http://quotes.toscrape.com/tag/humor/',
    ]

    def parse(self, response):
        for quote in response.css('div.quote'):
            yield {
                'text': quote.css('span.text::text').extract_first(),
                'author': quote.xpath('span/small/text()').extract_first(),
            }

        next_page = response.css('li.next a::attr("href")').extract_first()
        if next_page is not None:
            yield response.follow(next_page, self.parse)

```
将以上代码保存为`quotes_spider.py` 就可以了。进入你保存这个文件的目录，
然后后切换到我们的虚拟环境spider中运行`scrapy runspider quotes_spider.py -o quotes.json`就可以得到第一次抓取的数据了。

我们先简单说一下这段代码的意思，没有python基础也没有关系。但是我还是建议你去学习一下python，磨刀不误砍柴工嘛。

1. 导入Scrapy 库`import scrapy` 如果没有在正确的虚拟环境下运行的话呢，就会报错找不到scrapy之类的。
2. QuotesSpider是一个基于Spider 的对象，name 就是这个spider 的名字，scrapy 内部的调度器就会使用这个名字来运行spider
3. start_url 就是我们开始发送的url 通过这个地址，我们会得到一些网站服务器的反馈。当然一般情况下我们都不会使用这种方式。不要着急，我们后面会讲解的啦。
4. parse函数。 就是我们解析服务器反馈的函数咯，这里的parse 函数利用for 循环逐项解析了我们需要的内容。
5. next_page用于生成下一个url。
6. `scrapy runspider quotes_spider.py -o quotes.json` 这段命令运行我们之前保存的代码并将抓取的结果保存为一个json 格式的文件。

下一篇我们将介绍一点html 的内容，为未来抓取数据做一点点准备。

[1]:http://www.jianshu.com/p/94abd8eae128
[2]:https://docs.scrapy.org/en/latest/