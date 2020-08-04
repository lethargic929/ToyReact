# ToyReact
第一步:先新建一个文件夹
step2: npm init -y
step3: npm i webpack webpack-cli --sava-dev(注意这里一定要重启cmd的黑窗口)
step4: 新建一个文件webpack.config.js
step5: 新建一个文件 main.js
step6: 在webpack.config.js里输入以下代码
       module.exports={
  entry: {
    main:'./main.js'
  },
   module: {
    rules: [
      {
        test: /\.js$/,
        use:{
          loader:'babel-loader',
          options: {
            presets: ['@babel/preset-env'],
            plugins: [[
              '@babel/plugin-transform-react-jsx',
              {pragma:'ToyReact.createElement'}
            ]]
          }
        }
      }
    ]
  },
  mode:'development',
  optimization: {
    minimize:false
  }
}
step7: 新建一个文件main.html
step8: 在html文件里 输入<script src="./dist/main.js"></script>
step9: npm i babel-loader -save-dev
step10: npm i --save-dev @babel/core
step11: npm i --save-dev @babel/preset-env(babel所需要的环境)
step12: 新建一个文件ToyReact.js
        export let ToyReact={
  createElement () {
    debugger
  }
}
step13: 在main.js里引入ToyReact.js
