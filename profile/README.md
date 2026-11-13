# Velniko

我们在做 **[GeekSlope](https://geekslope.de5.net) 电脑租赁**：游戏本、轻薄本和工作站按天租用，从下单、签约、付款到交付、归还和退押金，全程在线完成。

整套系统跑在 Cloudflare 边缘网络上，加上一个装在每台出租电脑上的 Windows 客户端。

## 项目

| 仓库 | 是什么 | 技术 |
| --- | --- | --- |
| [**rent**](https://github.com/Velniko/rent) | 租赁业务主系统：客户、员工、管理员三个工作区，覆盖订单、在线合同、Stripe / 银行转账付款、交付归还、退款、发票、推荐佣金和 C2C 个人设备出租 | Cloudflare Workers · D1 · Hono · TypeScript |
| [**rent-web**](https://github.com/Velniko/rent-web) | 对外官网：设备、价格和库存实时读自主系统数据库，访客可直接注册并提交租赁申请，支持 Zoom2u 配送报价 | Cloudflare Workers · Hono SSR |
| [**rent-app**](https://github.com/Velniko/rent-app) | Windows 设备客户端：绑定设备、上报状态和验机信息、显示租期与到期提醒、执行授权的远程指令、自动更新 | .NET 8 · WinForms · Inno Setup |

```text
            Cloudflare D1（统一数据库）
                       │
               rent 后端 API
          ┌────────────┼────────────┐
     rent-web 官网   管理后台    rent-app 客户端
```

## 参与贡献

- 提交 Issue 或 PR 时会自动分配负责人。
- `main` 分支受保护，改动请通过 Pull Request 合并；CI 会自动运行测试 / 构建。
- 发现安全问题请不要公开提 Issue，参见 rent 仓库的 [SECURITY.md](https://github.com/Velniko/rent/blob/main/SECURITY.md)。
