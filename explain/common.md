
**基础**
    1. 开发环境
        NodeJS
        cnpm 
            `npm install -g cnpm --registry=https://registry.npm.taobao.org`
    2. 安装依赖
        1. 初始化 package.json 
            `cnpm init -y`
        2. 安装umi依赖
            `cnpm install umi --save-dev`
    3. 第一个页面
        1. 在 umi 中，大量的使用了配置和约定来帮助你快速开发代码。首先，我们先来创建配置文件。配置文件被约定为 config/config.js
            `export default {};`
        2. 在 umi 中，约定的存放页面代码的文件夹是 pages，是复数，不过如果你喜欢单数的话你配置项中你可以添加 singular 为 true 来让 page 变为约定的文件夹
        3. 约定式路由
            page 下面的 JS 文件都会按照文件名映射到一个路由
            `cnpm run [scriptname] `
        4. 配置式路由
            config.js
                `routes: [{
                    path: '/',
                    component: './HelloWorld',
                 }],`
        5. 添加 umi-plugin-react 插件
           umi 是一个可插拔的企业级 react 应用框架，它的很多功能都是通过插件实现。尤其是 umi 官方的 umi-plugin-react 这个插件集成了常用的一些进阶的功能，
           首先通过 
               `cnpm install umi-plugin-react --save-dev `
           来安装该插件集。然后在配置文件 config/config.js 中引入该插件
  
               export default {
                 plugins: [
                   ['umi-plugin-react', {
                   }],
                 ],
                 routes: [{
                   path: '/',
                   component: './HelloWorld',
                 }],
               }
        6. 构建和部署             
            cnpm install serve -g
            serve ./dist  