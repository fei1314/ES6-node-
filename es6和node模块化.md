node模块化：
        1.输出:exports.a=12;
            或者module.exports={
              a:12,
              b:5
            }
         2.引入：require('./a.js');
         3.引用自定义模块
            放到node_modules里
            前面加./

ES6模块化：
        一、输出
        export(a,b,c,...);
        二、引入
        import m from './a.js';
        三、例如：
            js文件夹下的a.js中
              let a=12;
              let b=5;
              export{a,b};
            a.html中
              import mod from './a.js';
              console.log(mod.a+mod.b);   //17
        四、用babel编译es6
          1.全局安装babel:cnpm i -g babel-cli
          2.新建文件夹babel_es6
          3.新建js文件夹，文件夹中新建a.js文件，a.js文件中写入es6代码
          4.新建a.html文件，引入a.js文件
          5.在命令行中进入babel_es6文件夹中：cd babel_es6
          6.执行npm init
          7.在生成的package.json文件中scripts加入: "build":"babel src -d build"
              其中src是源文件夹，build是编译后自动生成的文件夹，和src对应。
          8.新建文件.babelrc，该文件中的内容是
              {
                "presets":["env"]
              }
          9.在命令行中安装:cnpm install babel-preset-env --save-dev
          10.执行npm run build
          11.编译成功
