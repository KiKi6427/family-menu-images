# 家庭菜单点单

家庭/朋友聚会用的菜单点单小程序原型。浏览家常菜菜单、下单、添加心愿单（菜单外的菜）、花 ¥9.9 解锁菜谱。

## 技术选型

| 项目 | 选择 | 说明 |
|------|------|------|
| 平台 | 微信小程序 + Web 原型 | 小程序用于正式部署；Web 便于本地预览 |
| 支付 | Mock 确认框 | 生产环境接 WeChat Pay |
| 数据 | `data/dishes.json` → 生成 `miniprogram/data/dishes.js` | 48 道菜 + 完整菜谱 |
| UI | 亮色 + 品红主题 | #F7F7F8 背景 + #C51162 / #FF2D87 强调 |

## 快速预览（Web）

```bash
cd web
python3 -m http.server 8080
# 浏览器打开 http://localhost:8080
```

> 需通过 HTTP 服务打开（不能直接 file://），以便加载 `data/dishes.json`。

## 微信小程序（杜杜餐厅）

完整的中文部署与分享指南见 **[docs/miniprogram/](docs/miniprogram/)**。

### 快速开始

1. 在 [微信公众平台](https://mp.weixin.qq.com/) 注册小程序，获取 AppID
2. 将 AppID 写入 `miniprogram/project.config.json`（替换 `touristappid`）
3. 安装 [微信开发者工具](https://developers.weixin.qq.com/miniprogram/dev/devtools/download.html)
4. 导入项目，目录选 **`miniprogram/`**
5. **预览**（7 天临时二维码）或 **上传 → 体验版/正式版**（长期分享给朋友）

### 当前状态

- 48 道菜，图片全部本地化（`miniprogram/assets/dishes/`）
- 页面：菜单、详情、购物车、心愿单、历史订单
- 支付为 Mock 演示，不会真实扣款
- 菜单页支持分享卡片：「杜杜餐厅 · 来点菜呀」

## Cursor Skill

开发维护指南位于：

```
~/.claude/skills/family-menu-ordering/
├── SKILL.md
├── references/dishes.json
├── references/data-model.md
├── references/image-sources.md
└── evals/evals.json
```

## 功能清单

- [x] 菜单网格 + 分类筛选
- [x] 菜品详情 + 大图预览
- [x] 加入订单 / 购物车
- [x] 心愿单（自定义菜）
- [x] ¥9.9 菜谱解锁（mock）
- [x] 提交订单

## 下一步

1. 见 [docs/miniprogram/](docs/miniprogram/) 注册 AppID 并分享给朋友
2. 运行 skill evals 验证 skill 触发效果
3. （可选）接入云开发 + 订单通知主人
4. （可选）企业主体接入真实微信支付
