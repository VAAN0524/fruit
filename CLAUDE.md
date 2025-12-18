# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## 项目概述

这是一个基于Web的手势识别水果忍者游戏，使用MediaPipe Hands技术实现手势控制。项目包含单个HTML文件，集成了摄像头视频流、手势检测和游戏逻辑。

## 技术栈

- **前端**: HTML5, CSS3, JavaScript (ES6+)
- **手势识别**: MediaPipe Hands (@mediapipe/hands)
- **图形渲染**: Canvas 2D API
- **实时视频**: getUserMedia API + WebRTC
- **音频**: Web Audio API (用于切割音效)

## 核心架构

### 游戏组件
- **Fruit类**: 水果对象，处理抛物线运动、旋转和切割效果
- **Particle类**: 粒子系统，用于水果切割时的视觉效果
- **FruitNinjaGame类**: 主游戏引擎，管理游戏状态、碰撞检测和渲染

### 手势识别系统
- **Hands检测器**: 配置最多支持8只手（4人游戏）
- **Camera管理器**: 处理摄像头视频流和手势数据传输
- **碰撞检测**: 基于21个手部关键点的精确碰撞检测

### 渲染系统
- **双层次Canvas**: 游戏层叠加在视频流之上
- **镜像坐标转换**: 处理视频镜像效果下的手势坐标映射
- **实时渲染**: 60fps的游戏循环和手势可视化

## 开发要点

### 关键配置参数
- `maxNumHands: 8`: 最多支持8只手检测
- `minDetectionConfidence: 0.4`: 手势检测置信度阈值
- `spawnInterval: 1200ms`: 水果生成间隔
- `maxFruits: 5`: 屏幕最大水果数量

### 性能优化策略
- 手势检测点数限制（42点/手 = 336点总数）
- Canvas分层渲染减少重绘开销
- 粒子系统生命周期管理

### 多人游戏特性
- 支持1-4人同时游戏（每人2只手）
- 不同玩家手势用不同颜色区分
- 多人模式下得分奖励机制

## 常见开发任务

### 启动游戏
直接在浏览器中打开 `fruit_ninja_simple_hand.html` 文件，点击"开始手势识别游戏"按钮。

### 调试模式
游戏包含内置调试信息面板，显示：
- 模型加载状态
- 手势检测状态
- 识别点数统计
- 支持玩家数量

### 自定义配置
主要可调整参数位于以下位置：
- `FruitNinjaGame` 构造函数：游戏难度参数
- `initializeHands()` 函数：手势识别配置
- CSS样式：UI元素外观和布局

### 扩展功能建议
- 添加新的水果类型和特效
- 实现游戏难度递增系统
- 增加更多手势交互方式
- 添加本地存储高分功能