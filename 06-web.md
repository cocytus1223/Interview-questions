# 1. web

## 1.1. web 开发中会话跟踪的方法有哪些

1. cookie
2. session
3. url 重写
4. 隐藏 input
5. ip 地址

## 1.2. 前端需要注意哪些 SEO

1. 合理的 title、description、keywords：搜索对着三项的权重逐个减小，title 值强调重点即可，重要关键词出现不要超过 2 次，而且要靠前，不同页面 title 要有所不同；description 把页面内容高度概括，长度合适，不可过分堆砌关键词，不同页面 description 有所不同；keywords 列举出重要关键词即可
2. 语义化的 HTML 代码，符合 W3C 规范：语义化代码让搜索引擎容易理解网页
3. 重要内容 HTML 代码放在最前：搜索引擎抓取 HTML 顺序是从上到下，有的搜索引擎对抓取长度有限制，保证重要内容一定会被抓取
4. 重要内容不要用 js 输出：爬虫不会执行 js 获取内容
5. 少用 iframe：搜索引擎不会抓取 iframe 中的内容
6. 非装饰性图片必须加 alt
7. 提高网站速度：网站速度是搜索引擎排序的一个重要指标

## 1.3. 如何进行网站性能优化

- content 方面
  1. 减少 HTTP 请求：合并文件、CSS 精灵、inline Image
  2. 减少 DNS 查询：DNS 查询完成之前浏览器不能从这个主机下载任何任何文件。方法：DNS 缓存、将资源分布到恰当数量的主机名，平衡并行下载和 DNS 查询
  3. 避免重定向：多余的中间访问
  4. 使 Ajax 可缓存
  5. 非必须组件延迟加载
  6. 未来所需组件预加载
  7. 减少 DOM 元素数量
  8. 将资源放到不同的域下：浏览器同时从一个域下载资源的数目有限，增加域可以提高并行下载量
  9. 减少 iframe 数量
  10. 不要 404
- Server 方面
  1. 使用 CDN
  2. 添加 Expires 或者 Cache-Control 响应头
  3. 对组件使用 Gzip 压缩
  4. 配置 ETag
  5. Flush Buffer Early
  6. Ajax 使用 GET 进行请求
  7. 避免空 src 的 img 标签
- Cookie 方面
  1. 减小 cookie 大小
  2. 引入资源的域名不要包含 cookie
- css 方面
  1. 将样式表放到页面顶部
  2. 不使用 CSS 表达式
  3. 使用不使用@import
  4. 不使用 IE 的 Filter
- Javascript 方面
  1. 将脚本放到页面底部
  2. 将 javascript 和 css 从外部引入
  3. 压缩 javascript 和 css
  4. 删除不需要的脚本
  5. 减少 DOM 访问
  6. 合理设计事件监听器
- 图片方面
  1. 优化图片：根据实际颜色需要选择色深、压缩
  2. 优化 css 精灵
  3. 不要在 HTML 中拉伸图片
  4. 保证 favicon.ico 小并且可缓存
- 移动方面
  1. 保证组件小于 25k
  2. Pack Components into a Multipart Document

## 1.4. 什么是渐进增强

渐进增强是指在 web 设计时强调可访问性、语义化 HTML 标签、外部样式表和脚本。保证所有人都能访问页面的基本内容和功能同时为高级浏览器和高带宽用户提供更好的用户体验。核心原则如下:

- 所有浏览器都必须能访问基本内容
- 所有浏览器都必须能使用基本功能
- 所有内容都包含在语义化标签中
- 通过外部 CSS 提供增强的布局
- 通过非侵入式、外部 javascript 提供增强功能
- end-user web browser preferences are respected

## 1.5. doctype 是什么？

- DTD（document type definition，文档类型定义）是一系列的语法规则，用来定义 XML 或(X)HTML 的文件类型。浏览器会使用它来判断文档类型，决定使用何种协议来解析，以及切换浏览器模式。
  解读：DTD 就是告诉浏览器我是什么文档类型，那么浏览器根据这个来判断用什么引擎来解析渲染他。

- DOCTYPE 是用来声明文档类型和 DTD 规范的，一个主要的用途便是文件的合法性验证。如果文件代码不合法，那么浏览器解析时便会出一些差错。
  解读：DOCTYPE 通知浏览器当前文档的 DTD。

- 常见的 DOCTYPE

1. HTML 5
   `!DOCTYPE html`
2. HTML 4.01 Strict，严格模式，该 DTD 包含所有 HTML 元素和属性，但不包括展示型的和弃用的元素（比如 font）
   `<!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 4.01//EN" "http://www.w3.org/TR/html4/strict.dtd">`
3. HTML 4.01 Transitional，传统模式（宽松模式），该 DTD 包含所有 HTML 元素和属性，包括展示型的和弃用的元素（比如 font）
   `<!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 4.01 Transitional//EN" "http://www.w3.org/TR/html4/loose.dtd">`