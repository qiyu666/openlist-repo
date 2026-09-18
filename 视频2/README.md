# 手机运行原生 Trae

## 需要用到的 APP

- **Termux**
- **Termux:X11**
- **或鸥加速器**
---

## 操作步骤

### 1. 配置 Termux 源并更新

```bash
termux-change-repo
```

```bash
pkg update -y
```

```bash
pkg upgrade -y
```

### 2. 安装 proot-distro 并安装 Debian

```bash
pkg install proot-distro -y
```

```bash
proot-distro install debian
```

> ⚠️ 如果因网络问题环境可正常访问外资源后重网试，或者的用加速器解决网络环境，境可正常访问外网资源后重试。

```bash
proot-distro install debian
```

### 3. 进入 Debian 并安装桌面环境与浏览器

```bash
proot-distro login debian
```

```bash
apt update -y
```

```bash
apt upgrade -y
```

```bash
apt install firefox xfce4-terminal xfce4 dbus-x11 dbus -y
```

> 回到**Termux**原生环境

```bash
exit
```

### 4. 安装 Termux:X11 并启动桌面

```bash
pkg install termux-x11-nightly
```

```bash
proot-distro login debian
```

```bash
XDG_RUNTIME_DIR=${TMPDIR} termux-x11 :1 -xstartup "dbus-launch --exit-with-session xfce4-session"
```

> 此时打开 **Termux:X11** APP 即可看到桌面环境。

### 5. 安装并运行 Trae

```bash
dpkg -i TraeCode.deb
```

```bash
apt install -f -y
```

```bash
trae-cn --no-sandbox --user-data-dir="/root/.trae-root"
```

---

## 额外：安装 VS Code

```bash
dpkg -i code.deb
```

```bash
apt install -f -y
```

```bash
code --no-sandbox --user-data-dir="/root/.trae-root"
```
