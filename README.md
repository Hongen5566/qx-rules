# qx-rules

[blackmatrix7/ios_rule_script](https://github.com/blackmatrix7/ios_rule_script) 的定期镜像，只挑选 Quantumult X 用得上的 8 个规则集。

存在的理由只有一个：`raw.githubusercontent.com` 在部分网络环境下无法直连，走 jsDelivr CDN 才能稳定拉取。

## 来源与许可

| 项目 | 说明 |
|---|---|
| 上游 | [blackmatrix7/ios_rule_script](https://github.com/blackmatrix7/ios_rule_script) |
| 上游许可 | GPL-2.0 |
| 本仓库 | 原样镜像，内容未做任何修改，同样以 GPL-2.0 发布（见 [LICENSE](LICENSE)） |
| 版权 | 归上游作者所有，本仓库仅作分发，不主张任何原创权利 |

## 内容

| 文件 | 用途 | 大小 |
|---|---|---:|
| `rules/AdvertisingLite.list` | 去广告 | 1.4 MB |
| `rules/Apple.list` | 苹果服务 | 67 KB |
| `rules/OpenAI.list` | AI 服务 | 1.5 KB |
| `rules/YouTube.list` | YouTube | 6.8 KB |
| `rules/Netflix.list` | Netflix | 37 KB |
| `rules/Global.list` | 其他国外站点 | 1.2 MB |
| `rules/China.list` | 国内域名直连 | 116 KB |
| `rules/ChinaIPs.list` | 国内 IP 段直连 | 666 KB |

## 在 Quantumult X 中使用

```
https://fastly.jsdelivr.net/gh/Hongen5566/qx-rules@main/rules/China.list
```

配置示例：

```ini
[filter_remote]
https://fastly.jsdelivr.net/gh/Hongen5566/qx-rules@main/rules/AdvertisingLite.list, tag=🚦 去广告, force-policy=REJECT, update-interval=86400, enabled=true
```

> ⚠️ jsDelivr 只服务**公开**仓库。仓库一旦转为私有，所有链接立刻 404。

## 备用地址

jsDelivr 有多个入口，域名可互换：

- `https://cdn.jsdelivr.net/gh/Hongen5566/qx-rules@main/...`
- `https://fastly.jsdelivr.net/gh/Hongen5566/qx-rules@main/...`
- `https://gcore.jsdelivr.net/gh/Hongen5566/qx-rules@main/...`

如需完全绕开第三方 CDN，可在仓库 Settings → Pages 开启 GitHub Pages，然后改用：

```
https://hongen5566.github.io/qx-rules/rules/China.list
```

## 自动同步

`.github/workflows/sync.yml` 会在每天 UTC 03:00（北京时间 11:00）从上游拉取最新规则，内容有变化才提交。

也可在仓库的 **Actions → Sync rules → Run workflow** 手动触发。

## 说明

本仓库不含任何节点、订阅或凭据，仅包含公开的分流规则文本。
