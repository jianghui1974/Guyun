# 孤云 Guyun — 官网

孤云（Guyun）的产品官网，静态站点，托管在 GitHub Pages：
**<https://jianghui1974.github.io/Guyun/>**

不是应用源码仓库，也不托管安装包——所有下载都指向 App Store。

## 站点结构

```
/
├── index.html          简体中文（默认）
├── en/index.html       English
├── tw/index.html       繁體中文
├── styles.css          三语共用的一套样式
├── .nojekyll           关掉 Jekyll 处理，静态文件原样发布
└── assets/
    ├── app-icon*.png   App 图标（512 / 180 / favicon）
    ├── og*.png         社交分享图（三语各一张，1200×630）
    ├── cloud.svg       云纹（只作 favicon 之外的品牌点缀）
    └── shots/
        ├── zh/  en/    iphone-1..5、ipad-1..5、mac-1..5（WebP）
        └── tw/         繁中站点用的少量截图
```

## 本地预览

```sh
python3 -m http.server 8000
# 打开 http://127.0.0.1:8000/
```

直接双击 `index.html` 也能看，但用本地服务器更接近线上（语音、相对路径、`<dialog>` 行为都一致）。

## 改内容

- **文案**：三份 HTML 各自独立，改哪语改哪份；数字与事实以 App Store 上的描述和 `docs/COST-COMPARISON.md` 为准。
- **App Store 链接**：`https://apps.apple.com/{cn|us|tw}/app/id6809848348`，每页只放本语言对应的那一个，页脚再给另两个。
- **截图**：本次取自官方产品页 <https://www.godar.cn/products/guyun/> 的中英两套（各 5 张 × iPhone / iPad / Mac），已转成 WebP 并按设备宽度缩放。换新截图时按同一命名覆盖 `assets/shots/<lang>/`，宽高属性写在 HTML 里，别漏改。
- **样式**：品牌色 `--teal: #1F7573`（深色档 `#5CC7BD`），演示存储紫 `#6B52C7`，与 App 的设计规范一致。响应式断点 980 / 760 / 620。

## 部署

推 `main` 即发布（Pages 源：`main` 分支根目录）。改动后：

```sh
git add -A && git commit -m "content: ..." && git push
```

## 说明

- 价格区只给区间与口径，不承诺具体账单；以服务商官网为准。
- 没有放 ICP 备案号：备案属于 `godar.cn` 域名，不适用于 `github.io`。
- App 截图与图标版权归作者所有。
