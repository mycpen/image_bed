## 个人图床

### 本地发包

- 最近发包 2025-01-05，git push 时仅 `.npmignore` 和 `README.md` 发生变更
- 已发包 [2022](https://www.npmjs.com/package/mycpen-image-bed/v/0.0.0-2022)、2023、2024

1. 修改 `package.json`，改为去年年份。最后需回滚操作，见步骤 6

   ```diff
   {
     "name": "mycpen-image-bed",
   -  "version": "0.0.0-customSuffix",
   +  "version": "0.0.0-2024",
   ```

2. 相关命令，发布去年的包

   ```bash
   # https://blog.anheyu.com/posts/sdxhu.html#npm-镜像
   npm config set registry http://registry.npmmirror.com
   # 切回源
   npm config set registry https://registry.npmjs.org/
   
   # 仅第一次使用需要添加用户，之后会提示你输入你的npm账号密码以及注册邮箱
   npm adduser
   # 非第一次使用直接登录即可，之后会提示你输入你的npm账号密码以及注册邮箱
   npm login
   # 登出
   npm logout
   
   # 初始化
   npm init
   
   # 模拟 npm publish，提前演示哪些文件会被发布或者被忽略
   npm pack
   
   # 发布
   npm publish
   ```

3. 修改 `.npmignore`，新增去年年份

   ```bash
   # image/
   image/2022*
   image/2023*
   image/2024*
   # image/2025*
   
   ```

4. 网址

   https://www.npmjs.com/package/mycpen-image-bed

   https://npmmirror.com/package/mycpen-image-bed

5. cnpm sync

   https://github.com/mycpen/image_bed/actions/workflows/cnpm-sync-package.yml

   https://npmmirror.com/package/mycpen-image-bed/versions

6. 还原配置

   1. `package.json`，后缀为 -customSuffix

      ```diff
      {
        "name": "mycpen-image-bed",
      +  "version": "0.0.0-customSuffix",
      -  "version": "0.0.0-20xx,
      ```

   2. 本地 npm 配置

      ```bash
      # 使用 npmmirror 源
      npm config set registry http://registry.npmmirror.com
      
      # 登出
      npm logout
      ```

7. 推送变更 `bash git.sh`，仅 `.npmignore` 和 `README.md` 发生变更

8. 即时发布新版本

   https://github.com/mycpen/image_bed/actions/workflows/autopublish.yml

9. 同步变更 .github py 脚本

   https://github.com/mycpen/hexo-source

   https://github.com/mycpen/hexo-source-butterfly

   https://github.com/mycpen/hexo-source-diary

   https://github.com/mycpen/nav

