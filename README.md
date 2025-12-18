# 🍎 水果忍者 - 手势识别版

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![HTML5](https://img.shields.io/badge/HTML5-E34F26?logo=html5&logoColor=white)](https://developer.mozilla.org/en-US/docs/Glossary/HTML5)
[![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?logo=javascript&logoColor=black)](https://developer.mozilla.org/en-US/docs/Web/JavaScript)
[![MediaPipe](https://img.shields.io/badge/MediaPipe-FF6F00?logo=google&logoColor=white)](https://mediapipe.dev/)

一个基于Web技术的创新手势识别水果忍者游戏，使用MediaPipe Hands实现实时手势控制，支持多人同时游戏。

## 🎮 游戏特色

### 🤖 创新手势控制
- **实时手势识别**: 使用MediaPipe Hands技术，精确识别21个手部关键点
- **多人支持**: 最多支持4人同时游戏（8只手检测）
- **直观操作**: 挥手即可切割水果，无需任何设备

### 🎯 游戏体验
- **流畅动画**: 60fps高帧率渲染，丝滑的游戏体验
- **物理引擎**: 真实的抛物线运动和重力效果
- **粒子特效**: 水果切割时的华丽粒子爆炸效果
- **动态难度**: 水果生成频率和速度智能调整

### 🎨 视觉效果
- **镜像视频**: 实时摄像头视频流，镜像显示更自然
- **手势可视化**: 彩色手部骨架和关键点显示
- **玩家区分**: 不同玩家的手势用不同颜色标识
- **响应式设计**: 完美适配各种屏幕尺寸

## 🚀 快速开始

### 📋 系统要求
- 现代浏览器（Chrome 88+, Firefox 85+, Safari 14+）
- 摄像头设备
- HTTPS环境或localhost（摄像头权限要求）

### 🎮 直接游玩
1. 克隆或下载项目
```bash
git clone https://github.com/yourusername/fruit-ninja-hand-gesture.git
cd fruit-ninja-hand-gesture
```

2. 在浏览器中打开 `index.html`
3. 允许摄像头权限
4. 点击"🎮 开始手势识别游戏"按钮
5. 挥手开始切水果！

### 🌐 在线演示
访问在线演示链接：[演示地址]（如果部署了在线版本）

## 🛠️ 技术栈

### 核心技术
- **HTML5**: 页面结构和Canvas渲染
- **CSS3**: 响应式布局和动画效果
- **JavaScript ES6+**: 游戏逻辑和状态管理
- **MediaPipe Hands**: Google开源的手势识别框架

### API和库
- **WebRTC getUserMedia**: 摄像头访问
- **Canvas 2D API**: 游戏图形渲染
- **Web Audio API**: 动态音效生成
- **RequestAnimationFrame**: 流畅动画循环

## 🏗️ 项目架构

```
fruit-ninja-hand-gesture/
├── index.html                    # 主游戏文件
├── CLAUDE.md                     # 开发者文档
├── README.md                     # 项目说明
├── .gitignore                    # Git忽略文件
└── LICENSE                       # 开源许可证
```

### 核心组件

#### 🎮 游戏引擎
- **FruitNinjaGame**: 主游戏类，管理游戏状态和循环
- **Fruit**: 水果对象，处理运动和切割逻辑
- **Particle**: 粒子系统，视觉效果实现

#### 🤖 手势识别
- **Hands Detector**: MediaPipe手势检测配置
- **Camera Manager**: 摄像头视频流管理
- **Collision System**: 精确的手势-水果碰撞检测

#### 🎨 渲染系统
- **双Canvas层**: 视频层 + 游戏层
- **实时可视化**: 手势骨架和关键点渲染
- **坐标转换**: 镜像坐标系映射

## 📊 游戏特性

### 多人游戏模式
- **单人模式**: 标准水果忍者体验
- **多人模式**: 2-4人同时游戏，增加竞技性
- **得分系统**: 多人模式获得额外积分奖励

### 手势识别精度
- **21个关键点**: 每只手精确识别21个关键点
- **实时追踪**: 高帧率手势追踪，延迟极低
- **多手支持**: 同时检测最多8只手

### 游戏机制
- **抛物线运动**: 真实的物理引擎模拟
- **随机生成**: 7种水果类型，随机轨迹
- **难度递增**: 智能调整游戏节奏

## 🔧 配置选项

### 手势识别参数
```javascript
{
    maxNumHands: 8,           // 最多检测手数
    modelComplexity: 1,       // 模型复杂度 (0-2)
    minDetectionConfidence: 0.4,  // 检测置信度
    minTrackingConfidence: 0.4    // 追踪置信度
}
```

### 游戏参数
```javascript
{
    spawnInterval: 1200,      // 水果生成间隔(ms)
    maxFruits: 5,            // 屏幕最大水果数
    gravity: 0.24,           // 重力加速度
    bonusPoints: 10-15       // 得分奖励
}
```

## 🎯 游戏玩法

### 基础操作
1. **挥手切割**: 将手移动到水果附近即可切割
2. **多人协作**: 多个玩家可以同时切割不同水果
3. **得分机制**: 每个水果10分，多人模式15分

### 游戏技巧
- **预判轨迹**: 观察水果抛物线，提前准备
- **双手配合**: 利用双手可以同时切割多个水果
- **多人策略**: 与朋友分工，覆盖不同区域

## 🐛 故障排除

### 常见问题

**Q: 摄像头无法启动？**
A: 确保在HTTPS环境下或使用localhost，检查浏览器摄像头权限

**Q: 手势识别不准确？**
A: 确保光线充足，手部在摄像头视野内，避免快速移动

**Q: 游戏卡顿？**
A: 关闭其他标签页，使用性能较好的设备

**Q: 多人模式不工作？**
A: 确保所有玩家手部都在摄像头视野内，且不要遮挡

### 浏览器兼容性
| 浏览器 | 版本要求 | 支持状态 |
|--------|----------|----------|
| Chrome | 88+ | ✅ 完全支持 |
| Firefox | 85+ | ✅ 完全支持 |
| Safari | 14+ | ⚠️ 部分支持 |
| Edge | 88+ | ✅ 完全支持 |

## 🤝 贡献指南

欢迎贡献代码！请遵循以下步骤：

1. Fork 项目
2. 创建功能分支 (`git checkout -b feature/AmazingFeature`)
3. 提交更改 (`git commit -m 'Add some AmazingFeature'`)
4. 推送到分支 (`git push origin feature/AmazingFeature`)
5. 开启 Pull Request

### 开发建议
- 遵循现有代码风格
- 添加适当注释
- 测试新功能的兼容性
- 更新相关文档

## 📝 更新日志

### v1.0.0 (2024-01-XX)
- ✨ 初始版本发布
- 🎮 基础游戏功能
- 🤖 手势识别集成
- 👥 多人游戏支持
- 🎨 视觉效果优化

## 📄 许可证

本项目采用 MIT 许可证 - 查看 [LICENSE](LICENSE) 文件了解详情

## 🙏 致谢

- [MediaPipe](https://mediapipe.dev/) - 强大的手势识别框架
- [Google](https://developers.google.com/mediapipe) - MediaPipe技术支持
- [Canvas API](https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API) - 图形渲染支持

## 📞 联系方式

- 项目链接: [https://github.com/yourusername/fruit-ninja-hand-gesture](https://github.com/yourusername/fruit-ninja-hand-gesture)
- 问题反馈: [Issues](https://github.com/yourusername/fruit-ninja-hand-gesture/issues)
- 功能建议: [Discussions](https://github.com/yourusername/fruit-ninja-hand-gesture/discussions)

---

⭐ 如果这个项目对你有帮助，请给它一个星标！