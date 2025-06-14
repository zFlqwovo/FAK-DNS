# FAK-DNS for AdGuard Home

<p align="center">
  <img src="https://s2.loli.net/2024/01/04/N4QkHzlaSCIDbrt.jpg">
</p>

<p align="center">
  <b>AdGuard Home 中国特定配置，使用您最喜爱的 DNS 服务器</b><br>
  提高国内域名解析速度，全力避免 DNS 污染
</p>

<p align="center">
  <a href="https://github.com/Leev1s/FAK-DNS/stargazers">
    <img src="https://img.shields.io/github/stars/Leev1s/FAK-DNS?style=social" alt="Stars" />
  </a>
  <a href="https://github.com/Leev1s/FAK-DNS/blob/master/LICENSE">
    <img src="https://img.shields.io/github/license/Leev1s/FAK-DNS?color=blue" alt="MIT License"/>
  </a>
  <a href="https://github.com/Leev1s/FAK-DNS/actions">
    <img src="https://github.com/Leev1s/FAK-DNS/actions/workflows/convert.yml/badge.svg" alt="GitHub Actions Status"/>
  </a>
  <img src="https://img.shields.io/github/last-commit/Leev1s/FAK-DNS" alt="Last Commit" />
</p>

## 📌 主要特点


- 🧠 智能分流规则，**国内域名走中国 DNS，国外保持原样**
- 🔄 自动同步上游规则，**集成 GitHub Actions 自动更新**
- 📄 AdGuard Home 闪电⚡️导入


主要文件位于 [`converted`](./converted) 文件夹中：

| 文件名 | 描述 |
|--------|------|
| `FAK-DNS.txt` | 综合优化后的主规则文件（推荐使用） |
| `accelerated-domains.china.conf.txt` | 针对中国大陆优化的常用域名 |
| `google.china.conf.txt` | Google 中国服务域名加速（实验性） |
| `apple.china.conf.txt` | Apple 服务加速（遇到问题可选择性关闭） |


## ⚙️ 使用说明

本项目基于 [felixonmars/dnsmasq-china-list](https://github.com/felixonmars/dnsmasq-china-list) 自动同步规则，并通过 GitHub Actions 转换为 AdGuard Home 支持的格式。

- 默认设置：
  - 国内请求走 **阿里 DoH**
  - 国外请求走 **Cloudflare DoH**
  - 自动合并 Google / Apple / 中国域名加速规则

### 👉 **直接下载地址：**

<https://raw.githubusercontent.com/Leev1s/FAK-DNS/master/converted/FAK-DNS.txt>

## 📥 配置 AdGuard Home

1. 下载生成的 `FAK-DNS.txt` 文件
2. 放入 AdGuard Home 目录（一般为 `/opt/AdGuardHome/`）
3. 修改 `AdGuardHome.yaml`，添加以下配置：

```yaml
dns:
  upstream_dns_file: /opt/AdGuardHome/FAK-DNS.txt
```
4. 重启 AdGuard Home

## ✏️ 自定义配置

1. Fork 本仓库
2. 修改 Repository 中的 `CN_DNS` 与 `THE_DNS`，每行填写一个 DNS（DoH/DoT/QUIC/IP均可， `CN_DNS`填写您喜欢的国内DNS提供商，`THE_DNS`填写您信任的海外DNS提供商
3. 通过 Github Actions，生成你专属的规则文件
<p align="center">
  <img src="https://s2.loli.net/2024/01/02/86f3HDuQMzScewI.jpg">
</p>

## 🧾 License
This project contains code under multiple licenses.

- Original code from [upstream repo](https://github.com/felixonmars/dnsmasq-china-list) is licensed under the [WTFPL](./LICENSE-WTFPL).
- All modifications and additions by Lev1s are licensed under the MIT License. See [LICENSE](./LICENSE).

## 🌟 Star 一下？
如果你觉得这个项目对你有用，请给我一个小小的 Star

👉 <https://github.com/Leev1s/FAK-DNS>