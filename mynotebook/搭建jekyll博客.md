# 在GitHub上搭建jekyll

jkeyll中文教学文档
> [http://jekyllcn.com/docs/home/](http://jekyllcn.com/docs/home/)

### 上面未解决的问题

---

-  安装Ruby 

mac系统按照Linux源码编译即可
> 见：[http://www.runoob.com/ruby/ruby-installation-unix.html](http://www.runoob.com/ruby/ruby-installation-unix.html) 

---

- 安装RubyGems

使用ruby编译 setup.rb

> sudo ruby setup.rb

---

- 安装jekyll
	- 发生错误：
	`Unable to require openssl, install OpenSSL and rebuild ruby (preferred) or use non-HTTPS sources`
	注：找不到OpenSSL
	
> 解决方案 <br/>
> 先 `gem source -r https://rubygems.org/` to remove<br/>
> 后 `gem source -a http://rubygems.org/` to read

原文：
> url:`http://stackoverflow.com/questions/30825792/unable-to-require-openssl-when-trying-to-install-ruby-gems-on-os-x`

>Note: Calls to rubygems.org are deprecated - proceed with caution!

>I had the same issue on Mac OSX after also building ruby2.1.0p0 from the source. I already had openssl installed. It appears that the reference in gems needed refreshing. I ran:

> `gem source -r https://rubygems.org/` to remove

> followed by

> `gem source -a http://rubygems.org/` to read

>After this, I was able to run gems install bundler successfully.

>If you run into further errors, you can try ./configure --with-openssl-dir=/usr/local/ssl in your ruby downloaded dir/.


---

- 拓展：OpenSSL更新

知乎问题：`如何删除osx /usr/bin/openssl （系统自带）文件？`


>作者：半生在世
链接：http://www.zhihu.com/question/36693783/answer/69252578
来源：知乎
著作权归作者所有，转载请联系作者获得授权。

> 其实是自从OS X 10.11的El Captain开始引入的一个系统安全功能，叫做系统完整性保护，英文是System Integrity Protection，简称SIP，具体的官方说明可以参见：关于 Mac 上的系统完整性保护，在Mac社区中也被叫做rootless，本文后面使用SIP简称。它的主要目的是保护系统，尤其是系统内部的重要文件不被任意修改，即便是使用传统上被认为的Unix世界中的“上帝”，用户root，传统的Unix系统，只要使用root权限操作，它可以“杀死自己”。但是有了rootless，用户就有了把这个“上帝”控制在核心之外的能力，也就是，你这个“上帝”可以像从前一样任意妄为，只要是不变更受保护的系统文件。

> ## 禁止SIP
>OSX的用户，如果希望“暂时”禁止SIP，那么可以通过下面的方式：

>1. 关机后，开机的同时或者在听到开始音的同时，按住Command+R键
>2. 在出现 OS X Utilities后，选择Utilities下拉菜单中的Terminal
>3. 在打开的Terminal窗口中输入命令，并回车运行：
	
	csrutil disable; reboot

>你的Mac机会自动重新启动后，就启动到了SIP被禁止的状态。


>**一定要注意，禁止SIP后，系统随时有可能被恶意软件控制、系统被而已修改，一旦系统被恶意软件修改后，即便是再次打开SIP功能，系统依然可能被恶意软件控制。它只是禁止受签名保护软件被非法修改后的运行，但不能修复。**

> ## 开启SIP
> 重复前面“禁止SIP”的前两个步骤，第三不输入的命令改为：

	csrutil enable; reboot

>后话

>要说用户是自己OSX系统的上帝也不完全正确，因为我们只不过拥有一个禁止和打开SIP的手段而已。其实真正的“上帝”依然是Apple。OSX世界的创世纪者是Apple，从前是现在也是，它有这个天然的控制能力。要是你看看10.11的用户授权文档，也许会发现用户与OSX产品是以种租用者的身份使用的，这个方面的深入讨论不在此讨论之列。回归主题，其实在SIP框架下，有一种程序比root的权限还“大”，这就是Apple发布的软件，它们就有随意变更系统文件的能力。想想这也是可以理解的，如果Apple自己的软件都无法变更，那么OSX的系统更新岂不是要变得非常的麻烦？

>有人会问，为什么Apple发布的软件会有通过SIP的能力呢？其实这就好像在SIP中开了一个后门，只不过这个后门的钥匙，掌握在Apple手里，这个后门的钥匙就是Apple专有的私有程序签名证书，而SIP只对持有Apple签名的软件敞开大门。

>SIP是系统级别的全程保护，目前来说(2015年10月24日)还没有被攻破，或者说还没有人获得一把后门的备份钥匙。

>需要另外注意的是，并不是说有了SIP的保护，恶意软件就无法生存、没有价值了，其实，那种以偷取用户个人信息为目的的恶意软件，只要可以获取用户信息就可以了。所以，日常的安全意识还是要有的。

---

- 运行 jekyll serve 时错误：
> 		/usr/local/lib/ruby/site_ruby/2.3.0/rubygems/core_ext/kernel_require.rb:55:in `require': cannot load such file -- bundler (LoadError)
        from /usr/local/lib/ruby/site_ruby/2.3.0/rubygems/core_ext/kernel_require.rb:55:in `require'
        from /usr/local/lib/ruby/gems/2.3.0/gems/jekyll-3.2.1/lib/jekyll/plugin_manager.rb:34:in `require_from_bundler'
        from /usr/local/lib/ruby/gems/2.3.0/gems/jekyll-3.2.1/exe/jekyll:9:in `<top (required)>'
        from /usr/local/bin/jekyll:22:in `load'
        from /usr/local/bin/jekyll:22:in `<main>'




解决：
	`sudo gem install bundler
`



















