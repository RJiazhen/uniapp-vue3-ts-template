# uniapp-vue3-ts-template
基于官方模板自定义的uniapp+vue3+ts模板，预先添加了常用的pinia、sass、uni-ui等常用npm包，且在预设编译环境下编译为微信小程序时，没有因为不同版本的包导致的兼容性问题，开箱即用。

## 📥下载
在目标文件夹下执行以下命令：
```
npx degit RJiazhen/uniapp-vue3-ts-template my-project
```
将本仓库去除git配置后下载到本地，即可使用。

如因为网络问题无法下载，可以点击[该链接](https://gitee.com/Rjiazhen/uniapp-vue3-ts-template/archive/refs/tags/v1.0.0.zip)直接下载gitee仓库代码，解压后删除.git文件夹即可使用。

## ⏬ 运行

### 编译环境

本模板在`node.js 18.14.2`和`npm 9.5.0`环境下进行编译，其他环境下未测试

### 运行

#### 安装npm包：
```
npm install
```
注意，不要运行`npm audit fix --force`命令，可能会因为npm版本过高导致无法正常编译。
同时本模板在package.json中限制了pinia、sass、sass-loader的版本，请谨慎更新这几个库的版本，可能出现版本不兼容的问题。

#### 编译为开发环境的微信小程序：
```
npm run dev:mp-weixin
```
编译完成后，在微信开发者工具中导入运行，其他编译命令参考[uniapp官方文档](https://uniapp.dcloud.net.cn/quickstart-cli.html#%E8%BF%90%E8%A1%8C%E3%80%81%E5%8F%91%E5%B8%83uni-app)。

#### 编译为本地测试环境微信小程序：
```
npm run dev-local:mp-weixin
```
自定义环境配置参考[Vite官方文档](https://cn.vitejs.dev/guide/env-and-mode.html#modes)

#### 编译为生产环境的微信小程序：
```
npm run build:mp-weixin
```
该版本用于正式发行


## 💻 开发

### npm包

除原官方模板已自带的，本模板还添加了以下npm包：
* @dcloudio/uni-ui：uniapp官方ui库；
* @types/XXX：typescript类型包；
* @typescript-eslint/XXX：typescript的eslint插件；
* @uni-helper/XXX：uni-helper团队制作的uniapp的api的ts类型包；
* @vue/tsconfig: Vue官方提供的Vue3项目的ts配置；
* eslint、eslint-XXX：eslint及相关的配置扩展和插件，用于规范ts代码检查和风格规范；
* pinia：Vue官方推荐状态管理包；
* postcss-html：css样式转换器，用于stylelint；
* sass、sass-loader：scss语法支持，uni-ui必备；
* stylelint、stylelint-XXX：stylelint及相关配置扩展，用于样式代码的检查与风格规范；
* typescript：ts支持；
* unplugin-auto-import：自动引入vue、pinia、uniapp等的API；
* vite、vue-tsc：vite项目自带包；

### 开发环境和插件

推荐使用VScode进行开发，在插件搜索栏中输入`@recommended`可以查看本项目推荐使用的扩展。

**本项目推荐**的插件：

* [Volar](https://marketplace.visualstudio.com/items?itemName=Vue.volar)：Vue官方推荐插件，拥有语法检测、代码提示等适配Vue的功能，但注意使用时需要[开启Takeover模式](https://cn.vuejs.org/guide/typescript/overview.html#volar-takeover-mode)；
* [Eslint](https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint)：实时检测js/ts代码是否符合eslint配置，以及根据配置进行修复；
* [Auto Rename Tag](https://marketplace.visualstudio.com/items?itemName=formulahendry.auto-rename-tag)：自动重命名配对的HTML标签；
* [uni-create-view](https://marketplace.visualstudio.com/items?itemName=mrmaoddxxaa.create-uniapp-view)：快速创建uniapp视图；
* [uni-app-schemas](https://marketplace.visualstudio.com/items?itemName=uni-helper.uni-app-schemas-vscode)：校验 uni-app 中的 androidPrivacy.json、pages.json 和 manifest.json 格式；
* [uni-app-snippets](https://marketplace.visualstudio.com/items?itemName=uni-helper.uni-app-snippets-vscode)：uniapp代码片段；
* [uni-ui-snippets](https://marketplace.visualstudio.com/items?itemName=uni-helper.uni-ui-snippets-vscode)：uni-ui代码片段；
* [Stylelint](https://marketplace.visualstudio.com/items?itemName=stylelint.vscode-stylelint)：实时检测样式代码是否符合stylelint配置，以及根据配置进行修复；
* [Path Intellisense](https://marketplace.visualstudio.com/items?itemName=christian-kohler.path-intellisense)：路径提示。

  Eslint、Stylelint、Path Intellisense插件已在`.vscode\setting.json`中进行相关配置；

**其他推荐**插件：

* [Code Spell Checker](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker)：单词拼写检查；
* [Error Lens](https://marketplace.visualstudio.com/items?itemName=usernamehw.errorlens)：行内显示报错信息；
* [Todo Tree](https://marketplace.visualstudio.com/items?itemName=Gruntfuggly.todo-tree)：显示TODO、FIXME等特殊注释；

## 📖项目结构

```
uniapp-vue3-ts-template
├─ .eslintrc-auto-import.json       unplugin-auto-import自动生成文件，推荐添加到忽略列表
├─ .eslintrc.js                     eslint配置文件
├─ .stylelintrc.js                  stylelint配置文件
├─ .vscode                          VScode项目配置
├─ index.html
├─ package-lock.json
├─ package.json
├─ README.md
├─ src
│   ├─ api                          接口
│   │   ├─ request.ts               封装的请求方法
│   │   └─ user-api.ts              接口示例文件
│   ├─ App.vue
│   ├─ components                   组件
│   │   └─ MyPopup.vue              组件示例文件
│   ├─ env                          环境变量文件夹
│   │   ├─ .env.development         开发环境变量文件
│   │   ├─ .env.devLocal            本地开发环境变量文件
│   │   └─ .env.production          生产环境变量文件
│   ├─ main.ts
│   ├─ manifest.json                uniapp配置文件
│   ├─ pages                        页面
│   │   └─ index.vue                示例页面文件
│   ├─ pages.json                   项目页面配置文件
│   ├─ static                       静态文件夹
│   │   ├─ constants                常量
│   │   │   └─ view-constants.ts    常量示例文件
│   │   ├─ icons                    图标
│   │   │   └─ common               通用图标
│   │   ├─ images                   图片
│   │   │   └─ common               通用图片
│   │   └─ styles                   样式
│   │       └─ common.scss          通用样式文件
│   ├─ stores                       store文件夹
│   │   └─ user-store.ts            store示例文件
│   ├─ subpkg                       分包文件夹
│   │   └─ subpkg-example.vue       分包示例文件
│   ├─ types  类型
│   │   ├─ auto-imports.d.ts        unplugin-auto-import自动生成文件，推荐添加到忽略列表
│   │   ├─ env.d.ts                 全局类型示例文件
│   │   └─ shime-uni.d.ts           uniapp原模板自带声明文件
│   └─ utils                        通用方法
├─ tsconfig.json                    ts配置文件
├─ vite.config.ts                   vite配置文件
└─ vue.config.js                    vue配置文件
```

## 🦒代码风格
本项目推荐代码遵循[vue3官方的风格指南](https://v2.cn.vuejs.org/v2/style-guide/)和[Vue3组合式API风格指南（英文）](https://cn.vuejs.org/style-guide/)，js/ts代码风格已使用eslint进行限制，css/scss代码已使用stylelint进行限制。

以下是部分无法通过工具约束，但有希望遵循的规则

### 必要的

#### 优先使用`async/await`

除非是要将回调函数Promise化，否则优先使用`async/await`的形式代替`Promise.then()`，以免`Promise.then()`过度使用导致代码阅读难度增加。

#### 页面文件和组件文件的命名

页面文件使用短横线命名法（kebab-case），组件文件使用大驼峰命名法（PascalCase）。

除了uni-ui组件因为要使用easycom功能而使用短横线命名法，个人组件请使用大驼峰命名法，以便和Vue官方指南以及其他常见Vue组件库保持统一，而页面使用短横线命名法和组件文件进行区别。

#### 文件头部添加基本说明

在所有代码文件中添加类似以下的注释，以方便快速分辨文件作用：
```
<!-- 首页 -->

// 页面展示相关的常量

```

#### 给函数、变量添加注释

所有在外部使用的函数或变量均需要编写TSDoc风格的注释。

通过给函数或变量添加如下TSDoc风格注释，可以直接通过鼠标悬停就查看代码相关注释，以方便开发：
``` ts
/**
 * 显示弹窗
 * @param title 弹窗标题
 * @param icon 弹窗图标
 * @param duration 弹窗持续时间
 * @param mask 是否显示透明蒙层，防止触摸穿透
 * @param image 自定义图标的本地路径，image 的优先级高于 icon
 * @param success 成功回调
 * @param fail 失败回调
 * @param complete 完成回调
 * @returns void
 */
export const showToast = (
  title: string,
  icon: 'none' | 'success' | 'loading' | 'error' | undefined = 'none',
  duration = 1500,
  mask = false,
  image = '',
  success = () => { },
  fail = () => { },
  complete = () => { },
) => {
  uni.showToast({
    title,
    icon,
    duration,
    mask,
    image,
    success,
    fail,
    complete,
  })
}
```

详细编写方法可以参考[TSDoc官方文档](https://tsdoc.org/)。


#### 常量的命名和保存

对于菜单列表、数据模板这类不进行任何操作的常量，请保存在`src/static/constants`文件夹下对应的文件中，并且使用全大写下划线命名法，例如：
``` ts
// view-constants.ts

/** 首页按钮列表 */
export const HOME_BUTTON_LIST = [
  {
    name: '弹窗按钮一',
  },
  {
    name: '弹窗按钮二',
  },
  {
    name: '弹窗按钮三',
  },
]
```

## ✅TODO

- [ ] 编写完整的风格指南
- [ ] 编写项目开发建议
