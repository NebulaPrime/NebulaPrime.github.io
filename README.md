# 赛博空间 · gaozhuoran.com

个人主页占位版。纯静态，无依赖，双击 `index.html` 就能在本地看。

## 文件说明

| 文件 | 作用 |
|---|---|
| `index.html` | 页面本身。想改内容只动这个 |
| `CNAME` | 告诉 GitHub Pages 用 `gaozhuoran.com` 访问，**内容不能改** |
| `.nojekyll` | 让 GitHub 别用 Jekyll 处理文件，保持原样 |

## 上线步骤

### 1. 建仓库

GitHub 新建一个 **Public** 仓库，名字必须是：

```
NebulaPrime.github.io
```

（用户页仓库必须叫 `<用户名>.github.io`，免费账号只能用它开 Pages）

### 2. 传文件

把那三个文件（`index.html`、`CNAME`、`.nojekyll`）传到仓库根目录。
网页上传就行：仓库页 → Add file → Upload files → 把三个文件拖进去 → Commit。

### 3. 打开 Pages

仓库 → Settings → 左侧 Pages → Source 选 `Deploy from a branch` → Branch 选 `main` / `(root)` → Save。

等 1~2 分钟，访问 `https://NebulaPrime.github.io` 应该就能看到页面了。**这一步先确认能打开，再往下走。**

### 4. 配 DNS（先做这步）

阿里云 → 域名 → `gaozhuoran.com` → 解析设置 → 添加记录：

| 主机记录 | 类型 | 记录值 | TTL |
|---|---|---|---|
| `@` | A | `185.199.108.153` | 600 |
| `@` | A | `185.199.109.153` | 600 |
| `@` | A | `185.199.110.153` | 600 |
| `@` | A | `185.199.111.153` | 600 |
| `www` | CNAME | `NebulaPrime.github.io` | 600 |

**注意 CNAME 记录值结尾不要带点。**

### 5. 绑域名

回 GitHub → Settings → Pages → Custom domain 填 `gaozhuoran.com` → Save。
等 DNS check 通过（几分钟到几小时），然后勾上 **Enforce HTTPS**。

顺序不能反：先配 DNS，再填域名，否则 GitHub 会一直报 DNS check 失败，证书也签不出来。

### 6. 验证

- `https://gaozhuoran.com` 能打开且有小锁
- `http://gaozhuoran.com` 自动跳到 https

## 以后想加东西

改 `index.html`，提交，等一两分钟自动更新。不用重新配 DNS。

## 另一个域名

`gaozhuoran.me` 还没用。以后最省事的做法是在阿里云给它开「域名转发」跳到 `.com`，或者另开一个仓库放不同内容。
