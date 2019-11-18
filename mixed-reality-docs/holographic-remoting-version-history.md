---
title: 全息远程处理版本历史记录
description: HoloLens 2 上的全息远程处理的版本历史记录。
author: NPohl-MSFT
ms.author: nopohl
ms.date: 10/21/2019
ms.topic: article
keywords: HoloLens、远程处理、全息远程处理
ms.openlocfilehash: 9ff6a5f7594eb67dd4c1c8690812ab724cac9012
ms.sourcegitcommit: 2cf3f19146d6a7ba71bbc4697a59064b4822b539
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/12/2019
ms.locfileid: "73926652"
---
# <a name="holographic-remoting-version-history"></a>全息远程处理版本历史记录

> [!IMPORTANT]
> 本指南特定于 HoloLens 2 上的全息远程处理。

## 版本2.0.14 （2019年10月26日）<a name="v2.0.14"></a>
* 支持新的 PerceptionDevice Api （Windows 10 11 月2019更新）。
* 修复了阻止 SpatialGestureRecognizer 触发暂停手势事件的问题。
* 修复了使用 SpatialSurfaceObserver 时的线程处理问题。

## 版本2.0.12 （2019年10月18日）<a name="v2.0.12"></a>
* 修复了使用 NavigationRail （X/Y/Z）时 SpatialGestureRecognizer 中的崩溃。

## 版本 v2.0.10 （2019年10月10日）<a name="v2.0.10"></a>
* 修复了使用 VR 控制器的触发器按钮时出现故障。 全息远程处理并不完全支持控制器，如果与 HoloLens 2 配对，则仅触发器按钮和 Windows 按钮正常工作。

## 版本2.0.9 （2019年9月19日）<a name="v2.0.9"></a>
* 添加了对[SpatialAnchorExporter](https://docs.microsoft.com/uwp/api/windows.perception.spatial.spatialanchorexporter)的支持
* 添加了新的接口 ```IPlayerContext2``` （由 ```PlayerContext```实现），提供以下成员：
  - [BlitRemoteFrameTimeout](holographic-remoting-create-player.md#BlitRemoteFrameTimeout)属性。
* 已将 ```Failed_RemoteFrameTooOld``` 值添加到 ```BlitResult```
* 稳定性和可靠性改进

## 版本2.0.8 （2019年8月20日）<a name="v2.0.8"></a>

* 修复了使用[IDXGISurface2](https://docs.microsoft.com/windows/win32/api/dxgi1_2/nn-dxgi1_2-idxgisurface2)作为参数调用[HolographicCameraRenderingParameters](https://docs.microsoft.com/uwp/api/windows.graphics.holographic.holographiccamerarenderingparameters.commitdirect3d11depthbuffer)时的崩溃。
* 稳定性和可靠性改进

## 版本2.0.7 （2019年7月26日）<a name="v2.0.7"></a>

* 适用于 HoloLens 2 的全息远程处理的第一个公共版本。

## <a name="see-also"></a>另请参阅
* [编写自定义全息远程处理播放器应用程序](holographic-remoting-create-player.md)
* [编写全息远程处理主机应用](holographic-remoting-create-host.md)
* [全息远程处理故障排除和限制](holographic-remoting-troubleshooting.md)
* [全息远程处理软件许可条款](https://docs.microsoft.com/legal/mixed-reality/microsoft-holographic-remoting-software-license-terms)
* [Microsoft 隐私声明](https://go.microsoft.com/fwlink/?LinkId=521839)