# 动作Roguelike游戏 (课程项目)

此项目是**[使用C++和Unreal Engine进行专业游戏开发](https://courses.tomlooman.com/p/unrealengine-cpp?coupon_code=COMMUNITY15&src=github)**课程的一部分，我们将逐步构建这个游戏项目。

![课程标题](https://i0.wp.com/www.tomlooman.com/wp-content/uploads/2023/05/coursecpp_banner_widenarrow-3.png)

> **引擎版本：5.4**
>
> **课程代码使用分支“Lecture29-FinishedProject”**（UE 4.25，“主分支”包含额外的功能和扩展）

![GitHub分支选择信息](https://www.tomlooman.com/wp-content/uploads/2021/01/github_branchesinfo.jpg)

# 项目功能
- 第三人称动作角色移动
- **增强输入**
- **动作系统**（设计上类似Gameplay Ability System）
  - 冲刺能力（通过投射物传送）
  - 黑洞能力
  - 魔法投射攻击
  - “荆棘”增益（反射伤害）
  - 持续燃烧伤害效果
- 属性组件（持有生命值等）
- **保存游戏系统**用于持久化角色和世界状态的进度
- 基于事件的逻辑驱动UI和游戏反应
- 混合使用C++和蓝图并有效结合
- **GameplayTags**用于标记演员、增益、动作
- **多人游戏支持**所有功能
- 游戏模式逻辑
  - EQS用于绑定机器人/增益生成位置
  - 机器人生成系统（生成机器人需要积分，游戏模式会随时间增加积分以供使用）
  - DataTable保存机器人信息
  - DataAssets保存敌人配置
- **资产管理器**：异步加载数据资产
- 异步加载UI图标
- AI
  - 小兵AI使用行为树（漫游、观察、追逐、攻击、逃跑/治疗）
  - 自定义C++行为树节点
  - EQS用于AI的攻击/掩护位置
- 增益
  - 增益拾取用于治疗、获得积分/动作
-UMG
  - 主菜单用于创建/加入游戏
  - 玩家属性的UI元素和用于增益和敌人生命值的投影控件
  - C++本地化文本
- 实验性/进行中
  - 聚合计时（投射物）
  - 演员池（投射物）
- 异步线性追踪示例
- PSO预缓存及捆绑PSO设置用于Windows DX12

此项目是**[使用C++和Unreal Engine进行专业游戏开发](https://courses.tomlooman.com/p/unrealengine-cpp?coupon_code=COMMUNITY15&src=github)**课程的一部分，我们将逐步构建整个游戏项目。

![战斗示例静态图](https://www.tomlooman.com/wp-content/uploads/2023/02/Course_HeroBanner_TwoSplit_Narrow_1200.jpg)

# Unreal Engine 5

随着UE5的发布，一些新的渲染功能已经启用。对于低端机器，可能需要关闭这些功能。您可以通过项目设置或config INI进行设置。

### DefaultEngine.ini

```ini
[/Script/Engine.RendererSettings]
r.ReflectionMethod=1 ;lumen反射
r.GenerateMeshDistanceFields=True
r.DynamicGlobalIlluminationMethod=1 ;lumen全局照明
r.Shadow.Virtual.Enable=1 ;虚拟阴影贴图

[/Script/WindowsTargetPlatform.WindowsTargetSettings]
DefaultGraphicsRHI=DefaultGraphicsRHI_DX12 // 使用DX12以使用上述新渲染功能
```

**游戏资产**：仅授权用于Unreal Engine。没有自定义许可，您不能用于创建续集、重制版或以其他方式模仿原始游戏，或使用原始游戏的商标、角色名称或其他知识产权来宣传或命名您的游戏。（适用Unreal Engine EULA）（请注意，这适用于引用Epic的Paragon的游戏资产，您仍然可以使用项目代码和内容来构建您自己的Unreal Engine游戏）。