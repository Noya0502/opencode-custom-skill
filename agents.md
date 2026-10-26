# agents.md
## 项目硬性规则
1. 所有JavaScript变量名称、CSS类名、id名称，全部以hgj_作为前缀。
2. 所有HTML页面中都必须包含注释，注释内容：姓名：胡国静，日期：功能名称。
3. 项目只使用原生的HTML、CSS和JavaScript实现，禁止使用第三方库和CDN。
4. 图标统一使用font目录下的iconfont图标，禁止引入其他图标方案。
5. 获取服务器端数据一律使用fetch实现。
6. 在执行任何提示词任务之前，先把本次任务信息追加写入 hu406_prompt.md，采用附加模式，不能覆盖原有内容。
7. 写入hu406_prompt.md的固定格式：
==== 时间:yyyy-mm-dd-hh-mm | 模型名称:xxx | 提示词内容:xxx
时间严格使用 yyyy-mm-dd-hh-mm 格式。
8. 新建HTML页面必须添加超链接指向首页 index.html。
9. 每次新建或删除页面后，必须同步更新首页 index.html 的导航入口，保证首页可以进入项目中的全部页面。
10. HTML页面CSS必须使用px、rem、em、vw、%多种长度单位，并且实现CSS3 3D动画，使用 perspective、transform-style:preserve-3d、rotateX、rotateY。
