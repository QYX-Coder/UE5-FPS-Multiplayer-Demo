#  UE5 FPS 游戏 Demo — 第一人称射击游戏

> **课程作业**：UE游戏客户端开发实战课程 | 电子科技大学  
> **作者**：乔奕璇  
> **引擎版本**：Unreal Engine 5.7  
> **项目类型**：Blueprint 蓝图项目（基于 First Person 模板）

---

##  项目简介

本项目是基于 **Unreal Engine 5 官方第一人称（First Person）模板** 开发的 FPS 游戏 Demo，实现了完整的射击玩法循环：**AI 敌人战斗 → 玩家计分 → 通关胜利**，并支持 **多人局域网联机对战**。

---

##  核心功能

### 1.  AI 敌人系统
- 敌人可**自主寻路移动**，追踪玩家位置
- 敌人**主动攻击**玩家（近战/远程混合 AI 行为）
- 玩家可使用武器**射击击杀敌人**
- 支持多种敌人类型（普通丧尸、精英敌人）

### 2.  计分与胜利机制
- 实时击杀计分逻辑，UI 动态显示当前得分
- **通关胜利条件**：击杀全部敌人 + 收集完所有道具 → 触发胜利结算
- 胜利后展示最终得分与击杀统计

### 3.  多人局域网联机对战
- 基于 UE5 **网络同步架构（Replication）** 搭建
- 支持多名玩家在同一局域网内联机游玩
- **全网同步**：玩家位置、射击伤害、击杀计数、胜利结果实时同步
- 使用 Listen Server + Client 模式

### 4.  画面与交互
- 科幻风格场景（Modular Sci-Fi Station 资源包）
- UMG 血条/计分 HUD 界面
- 角色动画混合（移动 + 瞄准偏移）
- 死亡特效与音效反馈

---

##  操作说明

| 按键 | 功能 |
|------|------|
| `W/A/S/D` | 移动 |
| `鼠标` | 视角旋转 |
| `左键` | 射击 |
| `R` | 换弹 |
| `空格` | 跳跃 |
| `ESC` | 暂停菜单 |

---

##  项目结构

```
how2/
├── how2.uproject          # UE5 项目文件
├── Config/                # 项目配置（DefaultEngine.ini 等）
├── Content/               # 游戏资产（蓝图、地图、模型、贴图、动画）
│   ├── BP_AI.uasset       # AI 敌人蓝图
│   ├── AI_move.uasset     # AI 移动行为
│   ├── ZombieFemale/      # 丧尸敌人模型资源
│   ├── Survival_Character/ # 角色/武器模型
│   ├── ModularSciFiStation/ # 科幻场景资源包
│   ├── DramaticDeath/     # 死亡特效
│   └── umg-anmyhealth.uasset # 血条 UI
├── .gitignore             # Git 忽略规则
├── .gitattributes         # Git LFS 跟踪规则
└── 乔奕璇-电子科技大学-UE游戏客户端开发实战课程作业.mp4  # 完整演示视频
```

---

##  演示视频

项目仓库中包含完整游戏演示视频，展示了以下全流程：

1. 多人联机（双人）连接建立
2. 玩家协同作战 → 击杀 AI 敌人
3. 实时计分变化
4. 收集道具
5. 触发胜利条件 → 结算界面

<video src="https://github.com/QYX-Coder/UE5-FPS-Multiplayer-Demo/releases/download/v1.0.0/%E4%B9%94%E5%A5%95%E7%92%87-%E7%94%B5%E5%AD%90%E7%A7%91%E6%8A%80%E5%A4%A7%E5%AD%A6-UE%E6%B8%B8%E6%88%8F%E5%AE%A2%E6%88%B7%E7%AB%AF%E5%BC%80%E5%8F%91%E5%AE%9E%E6%88%98%E8%AF%BE%E7%A8%8B%E4%BD%9C%E4%B8%9A.mp4" controls width="100%"></video>

> ️ 如果视频无法在线播放，可直接 [下载观看](https://github.com/QYX-Coder/UE5-FPS-Multiplayer-Demo/releases/download/v1.0.0/%E4%B9%94%E5%A5%95%E7%92%87-%E7%94%B5%E5%AD%90%E7%A7%91%E6%8A%80%E5%A4%A7%E5%AD%A6-UE%E6%B8%B8%E6%88%8F%E5%AE%A2%E6%88%B7%E7%AB%AF%E5%BC%80%E5%8F%91%E5%AE%9E%E6%88%98%E8%AF%BE%E7%A8%8B%E4%BD%9C%E4%B8%9A.mp4)

---

## 交付说明

- ✅ **Windows 平台**：已完成完整打包，可独立运行
- ✅ 项目源码（Blueprint）完整上传至本仓库
- ✅ 完整演示视频已包含在仓库中，展示联机、打怪、计分、胜利全流程
- ⚠️ **Android APK**：因国内网络限制（Google 服务不可用），Android 构建工具链依赖的 Gradle/SDK 组件下载受阻，多次尝试均因网络问题失败。其他测试项已全部验证通过，被迫采用当前交付策略。

---

##  环境要求

| 环境 | 要求 |
|------|------|
| 引擎 | **Unreal Engine 5.7** |
| 平台 | Windows 10/11 (64-bit) |
| 显卡 | 支持 DirectX 12 的独立显卡 |
| 内存 | 建议 16GB+ |
| 网络 | 局域网环境（联机模式） |

---

##  快速开始

1. 克隆本仓库到本地
   ```bash
   git clone https://github.com/QYX-Coder/how2.git
   ```

2. 使用 **Unreal Engine 5.7** 打开 `how2.uproject`

3. 如需测试多人联机：
   - 在主菜单中选择 **Play → Net Mode → Play as Listen Server**
   - 另一台设备或编辑器窗口选择 **Play as Client**
   - 确保两台设备在同一局域网，或使用 `127.0.0.1` 本地测试

4. 游戏目标：击杀场景内所有 AI 敌人 + 收集全部道具，触发胜利！

---

##  参考资料与资源致谢

- Unreal Engine 5 First Person Template
- Modular Sci-Fi Station (Epic Marketplace)
- Zombie Female (Epic Marketplace)
- Survival Character Pack
- Dramatic Death Effects
- Infima Games Free Animations

---

##  License

本项目为课程作业用途，仅供学习参考。

---

**  Enjoy the game!  **
