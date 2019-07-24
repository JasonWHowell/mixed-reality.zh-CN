---
title: HoloLens 2 的 MR 教育共享模块
description: 完成本课程以了解如何在 HoloLens 2 应用程序中实现多用户共享体验。
author: jessemcculloch
ms.author: jemccull
ms.date: 02/26/2019
ms.topic: article
keywords: 混合现实, unity, 教程, hololens
ms.openlocfilehash: 3e4be00ddeab6d91dbbc8226bfa3dc543cded095
ms.sourcegitcommit: 611af6ff7a2412abad80c0c7d4decfc0c3a0e8c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/17/2019
ms.locfileid: "68293685"
---
# <a name="4-sharing-object-movements-with-multiple-users"></a>4.与多个用户共享对象移动

在本教程中, 我们将了解如何共享对象的移动, 以便共享会话的所有参与者都可以协同协作并彼此查看交互。 本课基于[基本模块教程](mrlearning-base.md)中构建的农历启动器构建。

目标

- 将农历启动器作为要共享的3D 模型
- 将项目配置为共享三维模型的变动。
- 了解如何构建基本的多用户协作应用程序

### <a name="instructions"></a>说明


1. 从上一课 (Ctrl + S) 保存场景。 可以将其命名为 HLSharedProjectMainPart4, 以便在需要时更轻松地找到它。

2. 在 "项目" 窗口的 "资产-> 脚本" 文件夹中, 双击 GenericNetSync 以在 Visual Studio 中打开它, 或使用的代码编辑器。  

![module3chapter4updatestep2](images/module3chapter4updatestep2.png)

3. 在34行和38行上, 删除//以激活将在本课中使用的表的代码。 接下来, 保存该文件。 

![module3chapter4updatestep3](images/module3chapter4updatestep3.png)

4. 在 "项目" 窗口中, 双击 "资产 > 脚本" 文件夹中的 PhotonRoom.cs 文件, 在 Visual Studio 中将其打开。 

![module3chapter4updatestep4](images/module3chapter4updatestep4.png)

5. 如步骤3中所示, 我们需要删除//以在第25行、第26行和第106行激活代码。

![module3chapter4updatestep5a](images/module3chapter4updatestep5a.png) 

![module3chapter4updatestep5b](images/module3chapter4updatestep5b.png)

6. 在层次结构视图中, 选择 "NetworkRoom" 对象。

![module3chapter4updatestep6](images/module3chapter4updatestep6.png)

7. 在 "项目" 视图中, 导航到 "资产-> 资源-> Prototyping"。 首先, 将表 prefab 拖放到 PhotonRoom 类中的 Tableprefab 槽。 接下来, 将 LunarModule prefab 拖放到 PhotonRoom 类上的 Module Prefab 槽。

![module3chapter4updatestep7](images/module3chapter4updatestep7.png)

   注意:如果单击其中一个 prefab 对象并发布, 检查器将切换到该对象。 单击、拖放, 然后将每个对象发布到相应的槽。

8. 单击 "MixedRealityPlayspace" 左侧的箭头, 将子游戏对象移到 "SharedPlayground prefab" 中。 接下来, 删除要删除的 prefab, MixedRealityPlayspace, 选择 prefab, 然后点击键盘上的 "删除"。
![Module3hapter4step5im](images/module3chapter4step5im.PNG)

>注意:请确保摄像机和 SharedPlayground 位置均设置为0、0和0。
>

9. 创建新的游戏对象, 并将其设置为 SharedPlayground 父对象的子对象, 以创建新的对象。 右键单击父对象, 然后选择 "创建空"。 

10. 在层次结构中选择新对象后, 请在 "检查器" 面板中将对象的名称更改为 TableAnchor。 另外, 单击 "添加组件", 然后搜索 "TableAnchor" 组件。 选择它并将其添加到对象。 

![Module3Chapter4step6im](images/module3chapter4step7im.PNG)

> 注意:将定位设置为 x = 1、y =-0.55 和 z = 2。 同时, 将旋转设置为 y = 90。 
>
> ![Module3Chapter4step6im](images/module3chapter4noteim.PNG)

11. 现在, 在 Prototyping 文件夹中的 "项目" 面板中, 将 "prefab" 表拖入刚刚创建的 "TableAnchor" 子对象。

![Module3Chapter4step8im](images/module3chapter4step8im.PNG)

12. 最后, 在 DebugWindow 对象中, 将 width 改为 50, 将其高度更改为20。

![Module3Chapter4step9im](images/module3chapter4step11im.PNG)

## <a name="congratulations"></a>祝贺


完成此工作后, 加入 Unity 项目的所有用户都可以绕过阴历启动器。 所有移动都将同步, 以便每个用户都可以看到彼此的交互。 这些概念用作功能齐全的共享协作体验的基本构建基块。 

尽管所有用户都作为共享体验的一部分进行连接, 并且可以看到对象的相对运动, 但是应用程序仍然无法准确地调整头像和对象, 以便本地用户在物理world. 为了定位本地共享体验, 每个设备都需要对物理环境有一个共同的了解。 在此模块中, 我们将使用将在下一课中实施的[Azure 空间锚点](<https://azure.microsoft.com/en-us/services/spatial-anchors/>)(ASA) 来实现此目的。

在继续学习下一课之前, 我们需要先完成 ASA 学习模块, 其中包含 ASA 基础知识、Azure 帐户和资源创建, 以及在我们可以将其集成到我们的共享体验之前所需的其他基本建筑块。

[下一课：共享 (Photon) 第5课](mrlearning-sharing(photon)-ch5.md)
