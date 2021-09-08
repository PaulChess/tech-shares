---
# try also 'default' to start simple
theme: seriph
# random image from a curated Unsplash collection by Anthony
# like them? see https://unsplash.com/collections/94734566/slidev
background: https://source.unsplash.com/collection/94734566/1920x1080
# apply any windi css classes to the current slide
class: 'text-center'
# https://sli.dev/custom/highlighters.html
highlighter: shiki
# show line numbers in code blocks
lineNumbers: false
# some information about the slides, markdown enabled
info: |
  ## Slidev Starter Template
  Presentation slides for developers.

  Learn more at [Sli.dev](https://sli.dev)
---

# hxm-vscode-download-icon插件

Presentation slides for developers

<div class="pt-12">
  <span @click="$slidev.nav.next" class="px-2 py-1 rounded cursor-pointer" hover="bg-white bg-opacity-10">
    Press Space for next page <carbon:arrow-right class="inline"/>
  </span>
</div>

<div class="abs-br m-6 flex gap-2">
  <button @click="$slidev.nav.openInEditor()" title="Open in Editor" class="text-xl icon-btn opacity-50 !border-none !hover:text-white">
    <carbon:edit />
  </button>
  <a href="https://github.com/slidevjs/slidev" target="_blank" alt="GitHub"
    class="text-xl icon-btn opacity-50 !border-none !hover:text-white">
    <carbon-logo-github />
  </a>
</div>


<!--
The last comment block of each slide will be treated as slide notes. It will be visible and editable in Presenter Mode along with the slide. [Read more in the docs](https://sli.dev/guide/syntax.html#notes)
-->

---
preload: false
layout: center
---

<segment-title>Background</segment-title>

---

# Daily Work On Downloading Icon

<br>
<br>

<v-clicks>

* 打开 [设计中台](https://datav.iwencai.com/resource/page/index.html#/iconfont)
* 搜索图标 -> 下载图标
* Repeat Step2
* 从杂乱的`Downloads`目录中找到刚刚下载的图标
* 将图标传输至内网
* 拷贝到项目的文件夹内
* Reapeat All

</v-clicks>

---
preload: false
layout: center
---

<h1>
  <img class="w-100 inline-block" src="/crazy.jpg" />
  <p v-motion
  :initial="{scale:2}"
  :enter="{scale: 1, transition: {duration: 600}}">Crazy! 😫</p>
</h1>

<style>
p {
  text-align: center;
  margin-top: 50px;
}
</style>

---
preload: false
layout: center
---

<h1>
  <img
    v-motion
    :initial="{ x: 200 }"
    :enter="{ x: 0 }"
    class="w-140 inline-block"
    src="/chat.jpg" />
</h1>

<style>
img {
  border-radius: 12px;
  border: 12px solid transparent;
  border-image: linear-gradient(to top, #F80, #2ED);
  border-image-slice: 10;
}
</style>

<!--
1. 这里可以讲一下站在我组件库这边的角度的痛点，Icon组件用不起来
2. Icon组件的心路历程
  2.1 常用组件库使用的ttf字体图标，但是我们的大多是色彩多样的svg
  2.2 svg-symbols.js 但是将设计中台的集成到组件库内部是不可能的，体积太大
  2.3 所以当时只内置了十多个图标在组件库内，10多k, 但是根本无法满足大家对于Icon的使用需求
3. 因此当时搁置了比较长的时间
-->

---
preload: false
layout: center
---

<h1 class="segment-title">
What is hxm-vscode-download-icon?
</h1>

---
preload: false
layout: center
---

# Demo

<br>

<video controls>
  <source src="/demo.mp4" type="video/mp4">
</video>

<style>
video {
  width: 700px;
}
</style>

<!--
1. 这里讲一下安装 简单给大家看一下 vscode market中的md
2. 一定要讲一下配合组件库如何使用，提前准备好demo
-->

---

# Main Feature

<div class="grid grid-cols-[1.5fr,4.2fr] gap-4">
  <div class="flex flex-col justify-center items-center pb-4">
    <img class="w-30 inline-block" src="/logo.png" />
    <h3 style="text-align: center">hxm-vscode-download-icon</h3>
  </div>
  <div class="border-l border-gray-400 border-opacity-25 !all:leading-12 !all:list-none my-auto">
    <ul>
      <li>1. 将Icon平台功能集成于vscode插件内，随开随用</li>
      <li>2. 支持通过图标英文名搜索后进行批量选择</li>
      <li>3. 支持剔除已选择的图标</li>
      <li>4. 支持批量导出svg文件夹</li>
      <li>5. 支持批量打包输出为svg-symbols.js 结合hxm-icon组件直接使用</li>
      <li>6. 支持缓存功能，下次打开页面的时候依然展示退出页面前的搜索及选择结果</li>
      <li>7. 内外网通用</li>
    </ul>
  </div>
</div>

---
preload: false
layout: center
---

<segment-title>Plugin FrameWork</segment-title>

---
layout: image-right
image: https://source.unsplash.com/collection/94734568/1920x1080
---

# FrameWork

- 一、vscode插件基础框架搭建
- 二、侧边栏图标及目录树配置
- 三、在vscode中创建webview
- 四、核心功能 Core:
  - 工具选择
  - 搜索图标功能
  - 搜索图标列表展示与联动
  - 已选择图标列表展示
  - vscode插件与webview的通信
  - 数据缓存
  - 内外网兼容
- 五、插件发布

[Plugin Todos: XMind文档下载地址](https://github.com/PaulChess/tech-shares/raw/master/vscode-icon-share/public/plugin-todos.xmind)

<!--
1. 这里带大家过一下xmind, 记得提前打开
-->

---
preload: false
layout: center
---

<segment-title>Code Implements</segment-title>

---
preload: false
layout: center
---

[1. VSCode插件基础教程](https://mp.weixin.qq.com/s/yYGeE1ZYwW2MZWGTYXWG1g)

<!--
1. 这里简单带大家过一下脚手架、安装、如何启动调试插件
2. extension.js插件入口介绍、 我理解的vscode核心: 指令 >new file >new folder
3. Open Webview Developer Tools
4. 5-10分钟之间
-->

---
preload: false
layout: center
---

2. 侧边栏配置

---

### 2.1 package.json 配置

```json {all|2-5|6|8-16|17-24|all}
{
  // 注册事件
  "activationEvents": [
    "onView: download_svg",
  ],
  // 注册视图
  "contributes": {
    "viewsContainers": {
      "activitybar": [
        {
          "id": "hxmui",
          "title": "SVG图标管理平台"
          "icon": "resources/sideIcon.svg"
        }
      ]
    },
    "views": {
      "hxmui": [
        {
          "id": "download_svg",
          "name": "同花顺Hux平台图标下载"
        },
      ]
    }
  }
}
```

<style>
.slidev-layout {
  padding-top: 1rem !important;
}
.slidev-layout h3 {
  margin-bottom: 0.2rem;
}  
</style>

<!--
1. viewsContainers: https://code.visualstudio.com/api/references/contribution-points#contributes.viewsContainers
2. views: https://code.visualstudio.com/api/references/contribution-points#contributes.views
3. 这里写个demo 带两个侧边栏
-->

---

### 2.2 sidebarTree.js 目录树配置

```javascript
module.exports = class SideBarTree {
  // 类中必须要实现的两个接口 
  getTreeItem(element) {
    return element;
  }
  getChildren() {
    // 在这里面注册children 
    const r_cates = [
      {
        title: 'Home',
        icon: 'home.svg'
      }
    ];
    const fin_items = [];
    for (let i = 0; i < c_rates.length; i++) {
      fin_items.push(
        new DataItem(
          /** 实例化 */
        )
      )
    }
  }
}

class DataItem extends vscode.TreeItem {}
```

<!--
1. Tree View: https://code.visualstudio.com/api/extension-guides/tree-view
-->

---
preload: false
layout: center
---

### 2.3 usage: **extension.js**

<br>

```javascript {2-9|all}
function active(context) {
  vscode.window.registerTreeDataProvider('download_svg', new SidebarTree(context));

  let openSite = vscode.commands.registerCommand('download_svg.openSite', () => {
    /**
     * 注册完事件的回调
     * 这里可以创建webview
     */
  })
}
```

---
preload: false
layout: center
---

3. 创建webview

---
preload: false
layout: center
---

### 3.1 注册webview panel

<br>

```javascript
const panel = vscode.window.createWebviewPanel(
  'webview',
  '同花顺Hxmui-Icon',
  vscode.ViewColumn.One,
  {
    enableScripts: true,
    retainContextWhenHidden: true
  }
);

panel.iconPath = vscode.Uri.file(join(__dirname, 'resources', 'home.svg'));
panel.webview.html = getWebViewContent(context, 'views/index.html');
```

<br>

[window.createWebviewPanel](https://code.visualstudio.com/api/references/vscode-api#window.createWebviewPanel)


<!--
1. 大概介绍一下里面的一些参数
-->

---
preload: false
layout: center
---

### 3.2 getWebViewContent 方法

<br>

```javascript
function getWebViewContent(context, templatePath) {
	const resourcePath = join(context.extensionPath, templatePath);
	const dirPath = dirname(resourcePath);
	let html = fs.readFileSync(resourcePath, 'utf-8');

    html = html.replace(/(<link.+?href="|<script.+?src="|<img.+?src=")(.+?)"/g, (m, $1, $2) => {
	  if ($2.indexOf("https://") < 0) {
        return $1 + vscode.Uri.file(resolve(dirPath, $2)).with({ scheme: 'vscode-resource' }).toString() + '"';
      } else {
        return $1 + $2 + '"';
      }
	});

	return html;
}
```

<!--
1. 大概解析一下这个函数的作用 { scheme: 'vscode-resource' }
-->

---
preload: false
layout: center
---

4. VS Code插件与Webview的通信

---
preload: false
layout: center
---

场景：用户在ui界面点击按钮的时候，文件/系统层面的工作需要由vscode去处理

<v-clicks>

* 生成svg-symbols.js
* 生成svg文件夹
* 设置本地缓存
* 获取本地缓存
* 清除本地缓存
  
</v-clicks>

---

<div>

webview中触发事件调用`vscode.postMessage`发送事件通知和参数

### index.html
```javascript
vscode.postMessage({
  command: 'exportSvgSymbolsFile',
  data: this.choosedList
})
```

</div>

<br>

<div v-click>

vscode插件一侧调用`panel.webview.onDidReceiveMessage`监听webview事件

### extension.js
```javascript
panel.webview.onDidReceiveMessage(
  async message => {
    switch(message.command) {
      case 'exportSvgSymbolsFile':
        break;
      case 'exportSvgFile':
        break;
      // 其他事件...
    }
  }
)
```

</div>

---
preload: false
layout: center
---

5. 生成svg-symbols

---

### 生成svg-symbols

1. `vscode.window.showSaveDialog` 调起保存弹窗，获取保存路径

2. 根据 `webview` 中返回的svg数组生成svg文件夹

3. 使用 `gulp-svg-symbols` 和 `gulp-svg-symbols2js` 输出 `svg-symbolsjs`

```javascript
function genSvgSymbolsJs(svgPath, outPath, callback = () => {}) {
  removeSync(outPath);
  return gulp
    .src(`${svgPath}/*.svg`)
    .pipe(svgSymbols())
    .pipe(svgSymbols2js())
    .pipe(gulp.dest(`${outPath}`))
    .on('end', () => { callback() })
}
```

---
preload: false
layout: center
---

6. 本地缓存

---

这里缓存用的是[lowdb](https://www.npmjs.com/package/lowdb)

1. 初始化

```javascript
const adapter = new FileSync(join(__dirname,'db.json'));
const db = low(adapter);

db.data = { posts: {} }; // 设置默认值
```

2. 设置缓存

```javascript
db.data.posts[message.key] = message.value;
```

3. 获取缓存 - 这里涉及到和webview的通信

```javascript
panel.webview.postMessage({ command: 'onGetStorageSuccess', data: db.data.posts[message.key] });
```

4. 清除缓存

```javascript
db.data.posts[message.key] = '';
```

---
preload: false
layout: center
---

7. 插件发布

---

# 插件发布的两种方式
* vsce package 发布vsix本地包
* vsce publish 发布到应用市场

<br>

有个坑需要注意一下:  
当我们在`package.json`中配置了`icon`属性，即应用的图标，但是没有指定repository仓库时，
发布的命令需要增加额外的参数：

```javascript
vsce publish --baseContentUrl https://none/ --baseImagesUrl https://none/

vsce package --baseContentUrl https://none/ --baseImagesUrl https://none/
```

---
preload: false
layout: center
---

<h1 class="segment-title">
References
</h1>

---
layout: image-left
image: https://source.unsplash.com/collection/94734568/1920x1080
---

# 参考资料
- [vscode官方文档](https://code.visualstudio.com/api/get-started/your-first-extension)
- [vscode webview](https://code.visualstudio.com/api/extension-guides/webview)
- [vscode TreeView](https://code.visualstudio.com/api/extension-guides/tree-view)
- [vscode插件与webview相互通信](https://zhouhangzooo.github.io/2019/04/03/vscode%E6%8F%92%E4%BB%B6%E4%B8%8Ewebview%E7%9B%B8%E4%BA%92%E9%80%9A%E4%BF%A1/)
- [lowdb 仓库](https://github.com/typicode/lowdb)
- [gulp-svg-symbols 仓库](https://github.com/Hiswe/gulp-svg-symbols)
- [gulp-svg-symbols2js 仓库](https://github.com/JofunLiang/gulp-svg-symbols2js)
- [VS Code 插件开发入门教程](https://mp.weixin.qq.com/s/yYGeE1ZYwW2MZWGTYXWG1g)
- [VSCode插件开发全攻略](https://www.cnblogs.com/liuxianan/p/vscode-plugin-overview.html#%E6%9C%89%E5%BF%85%E8%A6%81%E5%AD%A6%E4%B9%A0vscode%E6%8F%92%E4%BB%B6%E5%BC%80%E5%8F%91%E5%90%97)
- [VSCode WebView插件（扩展）开发实战](https://juejin.cn/post/6844903966799577101)
- [小霸王插件 仓库](https://github.com/gamedilong/anes)
- [我爱掘金插件 仓库](https://github.com/ezshine/vscode-ilovejuejin)

---
preload: false
layout: center
---

<h1 class="segment-title">
Thank You!
</h1>
