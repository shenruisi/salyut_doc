# <p align="center">Salyut</p>

<p align="center">A script engine of Trico</p>

**Salyut Engine** 是*trico script*的的解析引擎，通过简单的调用Salyut中方法，即可以运行*trico script*并得到相应的结果。**Salyut**是一个开源项目，您可以自行修改[expr]()目录下的类定制自己语法表达式，也可以通过修改/增加[token]()目录下的类来扩充**Salyut**的能力。

## 技术特点 ##

* 通过[Yaml]()来对词法进行解析，如果您对*Yaml*有一定的了解，可以更好的帮助您提升*trico script*的一些语言特性。

* 主要通过[Selenium]()来获取浏览器的操控和解析能力，如果您对*Selenium*有一定的了解可以更好的帮助您提升*trico script*的一些能力。

## 架构 ##
![](./img/architecture-cn.png)

## 许可证 ##
**Salyut Engine** 使用 [Apache 2.0](https://www.apache.org/licenses/LICENSE-2.0) 许可证，您可以免费下载，修改以及部署源代码。您还可以将 **Salyut Engine** 进行服务化封装，从而让**Salyut Engine** 具有更强大的业务处理能力。

**Salyut Engine** 还添加了[Commons Clause 1.0]()条款，对于您通过**Salyut Engine**进行服务化封装后进行售卖做了限制。当然我们还是希望**Salyut Engine**能够更好的作出开源贡献，所以如果您对如何商用**Salyut Engine**有更好的想法，请随时与我们联系[feedback@trico.cloud]()