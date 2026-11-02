# Leiden Campus Walk · 莱顿大学漫步

一个用纯 HTML + Canvas 写的单文件小游戏。没有依赖、没有构建步骤，双击 `index.html` 就能玩。

在线试玩：<https://hermanzeeman.github.io/leiden-campus-walk/>

## 玩法

- 电脑：方向键 / WASD 移动
- 手机：左下角虚拟摇杆移动，右下角 `E` 键进门 / 说话
- 走到门格子上会切换到相邻场景
- 靠近 NPC 按 `E` 交谈
- 对话中按 `E` 或空格继续

## 场景

| 场景 | 说明 |
| --- | --- |
| `yard` | 校园庭院，起点 |
| `lab` | 实验室主厅 |
| `lab_bench` | 实验台 |
| `lab_shelf` | 试剂架 |
| `obs` | 天文台 |

每个场景由 13 行 × 20 列的字符地图定义，`#` 为墙，`.` 为可走地面，`T` `L` `B` `W` `S` `C` `P` 为各类家具与障碍。

## 运行

```bash
# 直接打开
open leiden_campus.html

# 或者起个本地服务
python3 -m http.server 8000
# 然后访问 http://localhost:8000/leiden_campus.html
```

## 结构

整个游戏都在 `leiden_campus.html` 里：

- `<style>` — 页面与画布样式
- `SCENES` — 场景数据：地图、门、NPC、出生点
- `solidChars` — 碰撞判定用的实心字符集合
- `enter()` — 场景切换
- `loop()` — 主循环，负责绘制与输入处理

## 已知注意事项

对话文本里的换行必须写成 `\n` 转义。直接在双引号字符串里敲真实换行会让整个脚本解析失败，页面表现为纯黑屏。

## 许可

MIT
