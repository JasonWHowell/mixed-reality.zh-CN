---
title: OpenXR 入门
description: 开始使用 Windows Mixed Reality 和 HoloLens 2 耳机上的便携 OpenXR API 标准版。
author: thetuvix
ms.author: alexturn
ms.date: 2/28/2020
ms.topic: article
keywords: OpenXR，Khronos，BasicXRApp，windows Mixed Reality OpenXR 开发人员门户，DirectX，本机，本机应用，自定义引擎，中间件，入门，101，预览版扩展
ms.openlocfilehash: db45308834f920413420f080a35b378f6a55fa49
ms.sourcegitcommit: 536fd45b48a70bbeca1454cef517ae007225e533
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2020
ms.locfileid: "80362028"
---
# <a name="getting-started-with-openxr"></a><span data-ttu-id="08f6e-104">OpenXR 入门</span><span class="sxs-lookup"><span data-stu-id="08f6e-104">Getting started with OpenXR</span></span>

<span data-ttu-id="08f6e-105">可以使用 OpenXR 在 HoloLens 2 或 Windows Mixed Reality 上的 Windows Mixed 耳机上进行开发。</span><span class="sxs-lookup"><span data-stu-id="08f6e-105">You can develop using OpenXR on a HoloLens 2 or Windows Mixed Reality immersive headset on the desktop.</span></span>  <span data-ttu-id="08f6e-106">如果你无权访问耳机，则可以改用 HoloLens 2 模拟器或 Windows Mixed Reality 模拟器。</span><span class="sxs-lookup"><span data-stu-id="08f6e-106">If you don't have access to a headset, you can use the HoloLens 2 Emulator or the Windows Mixed Reality Simulator instead.</span></span>

## <a name="getting-started-with-openxr-for-hololens-2"></a><span data-ttu-id="08f6e-107">针对 HoloLens 2 的 OpenXR 入门</span><span class="sxs-lookup"><span data-stu-id="08f6e-107">Getting started with OpenXR for HoloLens 2</span></span>

<span data-ttu-id="08f6e-108">开始开发适用于 HoloLens 2 的 OpenXR 应用程序：</span><span class="sxs-lookup"><span data-stu-id="08f6e-108">To start developing OpenXR applications for HoloLens 2:</span></span>

1. <span data-ttu-id="08f6e-109">设置 HoloLens 2 或按照说明[安装最新版本的 hololens 2 模拟器](using-the-hololens-emulator.md)。</span><span class="sxs-lookup"><span data-stu-id="08f6e-109">Set up a HoloLens 2 or follow the instructions to [install a recent version of the HoloLens 2 emulator](using-the-hololens-emulator.md).</span></span>  <span data-ttu-id="08f6e-110">如果你的设备最近更新了其 OS，或者你使用的是最新的仿真程序映像，则应该已准备好 OpenXR 1.0。</span><span class="sxs-lookup"><span data-stu-id="08f6e-110">If your device has updated its OS recently or if you're using a recent emulator image, you should already have OpenXR 1.0 ready to go.</span></span>
1. <span data-ttu-id="08f6e-111">若要确保已获得最新的 OpenXR 运行时并提供所有[扩展](openxr.md#roadmap)，请在设备或模拟器中启动应用商店应用，打开右上方的菜单，单击 "**下载和更新**"，然后单击 "**获取更新**"。</span><span class="sxs-lookup"><span data-stu-id="08f6e-111">To make sure you've got the latest OpenXR runtime with all [extensions](openxr.md#roadmap) present, launch the Store app from within the device or emulator, open the menu in the upper-right, click **Downloads and updates** and click **Get updates**.</span></span>  <span data-ttu-id="08f6e-112">这可确保 HoloLens 上的 OpenXR 运行时是最新的。</span><span class="sxs-lookup"><span data-stu-id="08f6e-112">This ensures that the OpenXR runtime on your HoloLens is up to date.</span></span>  <span data-ttu-id="08f6e-113">请注意，如果使用的是模拟器，则每次启动时都会重置模拟器映像，因此最好的做法是确保使用[最新版本的 HoloLens 2 模拟器映像](using-the-hololens-emulator.md)。</span><span class="sxs-lookup"><span data-stu-id="08f6e-113">Note that if you're using the emulator, the emulator image will reset each time you start it, and so your best bet is to just make sure that you have [the latest version of the HoloLens 2 emulator image](using-the-hololens-emulator.md).</span></span>

## <a name="getting-started-with-openxr-for-windows-mixed-reality-headsets"></a><span data-ttu-id="08f6e-114">OpenXR for Windows Mixed Reality 耳机入门</span><span class="sxs-lookup"><span data-stu-id="08f6e-114">Getting started with OpenXR for Windows Mixed Reality headsets</span></span>

<span data-ttu-id="08f6e-115">开始为沉浸式 Windows Mixed Reality 耳机开发 OpenXR 应用程序：</span><span class="sxs-lookup"><span data-stu-id="08f6e-115">To start developing OpenXR applications for immersive Windows Mixed Reality headsets:</span></span>

1. <span data-ttu-id="08f6e-116">请确保至少运行 Windows 10 2019 更新（1903），这是 Windows Mixed Reality 最终用户运行 OpenXR 应用程序的最低要求。</span><span class="sxs-lookup"><span data-stu-id="08f6e-116">Be sure you are running at least the Windows 10 May 2019 Update (1903), which is the minimum requirement for Windows Mixed Reality end users to run OpenXR applications.</span></span>  <span data-ttu-id="08f6e-117">如果你使用的是早期版本的 Windows 10，则可以使用<a href="https://www.microsoft.com/software-download/windows10" target="_blank">windows 10 更新助手</a>进行升级。</span><span class="sxs-lookup"><span data-stu-id="08f6e-117">If you're on an earlier version of Windows 10, you can upgrade by using the <a href="https://www.microsoft.com/software-download/windows10" target="_blank">Windows 10 Update Assistant</a>.</span></span>
2. <span data-ttu-id="08f6e-118">设置 Windows Mixed Reality 耳机，或按照说明[启用 Windows Mixed reality 模拟器](using-the-windows-mixed-reality-simulator.md)。</span><span class="sxs-lookup"><span data-stu-id="08f6e-118">Set up a Windows Mixed Reality headset or follow the instructions to [enable the Windows Mixed Reality simulator](using-the-windows-mixed-reality-simulator.md).</span></span>  <span data-ttu-id="08f6e-119">设置 Windows Mixed Reality 时，混合现实门户会自动安装 Windows Mixed Reality OpenXR 运行时。</span><span class="sxs-lookup"><span data-stu-id="08f6e-119">As you set up Windows Mixed Reality, Mixed Reality Portal will automatically install the Windows Mixed Reality OpenXR Runtime.</span></span>  <span data-ttu-id="08f6e-120">然后，Microsoft Store 会使运行时保持最新状态。</span><span class="sxs-lookup"><span data-stu-id="08f6e-120">The Microsoft Store will then keep the runtime up to date.</span></span>
3. <span data-ttu-id="08f6e-121">通过从 "开始" 菜单启动混合现实门户，并单击 .。。菜单，然后选择 "设置 OpenXR"。</span><span class="sxs-lookup"><span data-stu-id="08f6e-121">Make the Windows Mixed Reality OpenXR Runtime active by launching Mixed Reality Portal from the Start menu, clicking the ... menu in the lower-left and selecting "Set up OpenXR".</span></span><br>
<span data-ttu-id="08f6e-122">![在混合现实门户中设置 OpenXR](images/mixed-reality-portal-set-up-openxr.png)</span><span class="sxs-lookup"><span data-stu-id="08f6e-122">![Setting up OpenXR in the Mixed Reality Portal](images/mixed-reality-portal-set-up-openxr.png)</span></span>

<span data-ttu-id="08f6e-123">如果需要让 Windows Mixed Reality OpenXR 运行时再次激活，请重复步骤3。</span><span class="sxs-lookup"><span data-stu-id="08f6e-123">If you ever need to make the Windows Mixed Reality OpenXR Runtime active again, repeat step 3.</span></span>

> [!NOTE]
> <span data-ttu-id="08f6e-124">对于所有 Windows Mixed Reality 最终用户，Windows Mixed Reality OpenXR 运行时即将自动变为活动状态。</span><span class="sxs-lookup"><span data-stu-id="08f6e-124">The Windows Mixed Reality OpenXR Runtime will soon be made active automatically for all Windows Mixed Reality end users.</span></span>

## <a name="getting-the-windows-mixed-reality-openxr-developer-portal"></a><span data-ttu-id="08f6e-125">获取 Windows Mixed Reality OpenXR 开发人员门户</span><span class="sxs-lookup"><span data-stu-id="08f6e-125">Getting the Windows Mixed Reality OpenXR Developer Portal</span></span>

<span data-ttu-id="08f6e-126">若要尝试 Windows Mixed Reality OpenXR 运行时，可以安装<a href="https://www.microsoft.com/store/productId/9n5cvvl23qbt" target="_blank">混合现实 OpenXR 开发人员门户应用程序</a>。</span><span class="sxs-lookup"><span data-stu-id="08f6e-126">To try out the Windows Mixed Reality OpenXR Runtime, you can install the <a href="https://www.microsoft.com/store/productId/9n5cvvl23qbt" target="_blank">Mixed Reality OpenXR Developer Portal app</a>.</span></span>  <span data-ttu-id="08f6e-127">此应用程序提供了演示 OpenXR 的各种功能的演示场景，同时提供了一个系统状态页，其中提供了有关活动运行时和当前耳机的关键信息。</span><span class="sxs-lookup"><span data-stu-id="08f6e-127">This app provides a demo scene that exercises various features of OpenXR, along with a System Status page that provides key information about the active runtime and the current headset.</span></span>

<span data-ttu-id="08f6e-128">如果使用模拟器，安装混合现实 OpenXR 开发人员门户的最简单方法是使用[Windows 设备门户](using-the-windows-device-portal.md)，通过导航到 "OpenXR" 页，然后单击 "开发人员功能" 下的 "安装" 按钮。</span><span class="sxs-lookup"><span data-stu-id="08f6e-128">If using the emulator, the easiest way to install the Mixed Reality OpenXR Developer Portal is using [Windows Device Portal](using-the-windows-device-portal.md), by navigating to the "OpenXR" page and then clicking the "Install" button under "Developer Features".</span></span> <span data-ttu-id="08f6e-129">（这也适用于物理 HoloLens 2 设备）</span><span class="sxs-lookup"><span data-stu-id="08f6e-129">(this works on a physical HoloLens 2 device as well)</span></span>

![混合现实 OpenXR 开发人员门户应用](images/mixed-reality-openxr-developer-portal.png)

## <a name="building-a-sample-openxr-app"></a><span data-ttu-id="08f6e-131">生成示例 OpenXR 应用</span><span class="sxs-lookup"><span data-stu-id="08f6e-131">Building a sample OpenXR app</span></span>

<span data-ttu-id="08f6e-132">如果尚未安装，请务必安装 OpenXR 开发所需[的工具](install-the-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="08f6e-132">Be sure to [install the tools](install-the-tools.md) you'll need for OpenXR development if you haven't already.</span></span>

<span data-ttu-id="08f6e-133"><a href="https://github.com/microsoft/OpenXR-MixedReality/tree/master/samples/BasicXrApp" target="_blank">BasicXrApp</a>项目演示了一个简单的 OpenXR 示例，其中包含两个 Visual Studio 项目文件，一个用于 Win32 桌面应用，另一个用于 UWP HoloLens 2 应用。</span><span class="sxs-lookup"><span data-stu-id="08f6e-133">The <a href="https://github.com/microsoft/OpenXR-MixedReality/tree/master/samples/BasicXrApp" target="_blank">BasicXrApp</a> project demonstrates a simple OpenXR sample with two Visual Studio project files, one for both a Win32 desktop app and one for a UWP HoloLens 2 app.</span></span>  <span data-ttu-id="08f6e-134">由于解决方案包含一个 HoloLens UWP 项目，因此需要在 Visual Studio 中安装[通用 Windows 平台开发工作负载](install-the-tools.md#installation-checklist)才能完全打开它。</span><span class="sxs-lookup"><span data-stu-id="08f6e-134">Because the solution contains a HoloLens UWP project, you'll need the [Universal Windows Platform development workload](install-the-tools.md#installation-checklist) installed in Visual Studio to fully open it.</span></span>

<span data-ttu-id="08f6e-135">请注意，虽然 Win32 和 UWP 项目文件是独立的，但由于打包和部署的不同，每个项目中的应用代码都是100%。</span><span class="sxs-lookup"><span data-stu-id="08f6e-135">Note that while the Win32 and UWP project files are separate due to differences in packaging and deployment, the app code inside each project is 100% the same!</span></span>

<span data-ttu-id="08f6e-136">生成 OpenXR 的 Win32 桌面后。EXE，无论是 Windows Mixed Reality 耳机还是任何其他耳机，都可以在任何支持 OpenXR 的 desktop VR 平台上将它与 VR 耳机一起使用。</span><span class="sxs-lookup"><span data-stu-id="08f6e-136">After building an OpenXR Win32 desktop .EXE, you can use it with a VR headset on any desktop VR platform that supports OpenXR, whether it's a Windows Mixed Reality headset or any other headset.</span></span>

<span data-ttu-id="08f6e-137">生成 OpenXR UWP 应用包后，可以将[该包部署](using-visual-studio.md)到 hololens 2 设备或 Hololens 2 仿真器。</span><span class="sxs-lookup"><span data-stu-id="08f6e-137">After building an OpenXR UWP app package, you can [deploy that package](using-visual-studio.md) to either a HoloLens 2 device or the HoloLens 2 Emulator.</span></span>

## <a name="integrate-the-openxr-loader-into-a-project"></a><span data-ttu-id="08f6e-138">将 OpenXR 加载程序集成到项目中</span><span class="sxs-lookup"><span data-stu-id="08f6e-138">Integrate the OpenXR loader into a project</span></span>

<span data-ttu-id="08f6e-139">若要开始在现有项目中使用 OpenXR，你将包含 OpenXR 加载程序。</span><span class="sxs-lookup"><span data-stu-id="08f6e-139">To get started with OpenXR in an existing project, you'll include the OpenXR loader.</span></span>  <span data-ttu-id="08f6e-140">加载程序在设备上发现活动的 OpenXR 运行时，并提供对它实现的核心函数和扩展函数的访问权限。</span><span class="sxs-lookup"><span data-stu-id="08f6e-140">The loader discovers the active OpenXR runtime on the device and provides access to the core functions and extension functions that it implements.</span></span>

<span data-ttu-id="08f6e-141">你可以从 Visual Studio 项目中[引用官方 OpenXR NuGet 包](#reference-official-openxr-nuget-package)，也可以包括 Khronos GitHub 存储库中[的官方 OpenXR 加载器源](#include-official-openxr-loader-source)。</span><span class="sxs-lookup"><span data-stu-id="08f6e-141">You can either [reference the official OpenXR NuGet package](#reference-official-openxr-nuget-package) from your Visual Studio project or [include the official OpenXR loader source](#include-official-openxr-loader-source)  from the Khronos GitHub repo.</span></span>  <span data-ttu-id="08f6e-142">这两种方法都可让你访问 OpenXR 1.0 核心功能，以及 `EXT` 和 `MSFT` 扩展的发布 `KHR`。</span><span class="sxs-lookup"><span data-stu-id="08f6e-142">Either approach will give you access to OpenXR 1.0 core features, plus published `KHR`, `EXT` and `MSFT` extensions.</span></span>

<span data-ttu-id="08f6e-143">如果你有兴趣试用 `MSFT_preview` 扩展，则可以从混合现实 GitHub 存储库[复制预览版 OpenXR 标头](#using-preview-extensions)。</span><span class="sxs-lookup"><span data-stu-id="08f6e-143">If you're interested to experiment with `MSFT_preview` extensions as well, you can [copy in preview OpenXR headers](#using-preview-extensions) from the Mixed Reality GitHub repo.</span></span>

### <a name="reference-official-openxr-nuget-package"></a><span data-ttu-id="08f6e-144">引用官方 OpenXR NuGet 包</span><span class="sxs-lookup"><span data-stu-id="08f6e-144">Reference official OpenXR NuGet package</span></span>

<span data-ttu-id="08f6e-145"><a href="https://www.nuget.org/packages/OpenXR.Loader/" target="_blank"> **OpenXR** NuGet 包</a>是引用预生成的 OpenXR 加载程序的最简单方法。在 Visual Studio C++解决方案中的 DLL。</span><span class="sxs-lookup"><span data-stu-id="08f6e-145">The <a href="https://www.nuget.org/packages/OpenXR.Loader/" target="_blank">**OpenXR.Loader** NuGet package</a> is the easiest way to reference a prebuilt OpenXR loader .DLL in your Visual Studio C++ solution.</span></span>  <span data-ttu-id="08f6e-146">这样，你就可以访问 OpenXR 1.0 核心功能，还可以访问发布的 `KHR``EXT` 和 `MSFT` 扩展。</span><span class="sxs-lookup"><span data-stu-id="08f6e-146">This will give you access to OpenXR 1.0 core features, plus published `KHR`, `EXT` and `MSFT` extensions.</span></span>

<span data-ttu-id="08f6e-147">若要将 OpenXR NuGet 包引用添加到你的 Visual Studio C++解决方案，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="08f6e-147">To add an OpenXR.Loader NuGet package reference to your Visual Studio C++ solution:</span></span>
1. <span data-ttu-id="08f6e-148">在**解决方案资源管理器**中，右键单击将使用 OpenXR 的项目，然后选择 "**管理 NuGet 包 ...** "。</span><span class="sxs-lookup"><span data-stu-id="08f6e-148">In **Solution Explorer**, right-click the project that will use OpenXR and select **Manage NuGet Packages...**.</span></span>
1. <span data-ttu-id="08f6e-149">切换到 "**浏览**" 选项卡并搜索**OpenXR**。</span><span class="sxs-lookup"><span data-stu-id="08f6e-149">Switch to the **Browse** tab and search for **OpenXR.Loader**.</span></span>
1. <span data-ttu-id="08f6e-150">选择**OpenXR**包，然后在右侧的详细信息窗格中单击 "安装"。</span><span class="sxs-lookup"><span data-stu-id="08f6e-150">Select the **OpenXR.Loader** package and click Install in the details pane to the right.</span></span>
1. <span data-ttu-id="08f6e-151">单击 "确定" 以接受对项目所做的更改。</span><span class="sxs-lookup"><span data-stu-id="08f6e-151">Click OK to accept the changes to your project.</span></span>
1. <span data-ttu-id="08f6e-152">将 `#include <openxr/openxr.h>` 添加到源文件，开始使用 OpenXR API。</span><span class="sxs-lookup"><span data-stu-id="08f6e-152">Add `#include <openxr/openxr.h>` to a source file to start using the OpenXR API.</span></span>

<span data-ttu-id="08f6e-153">若要查看 OpenXR API 的运行示例，请查看<a href="https://github.com/microsoft/OpenXR-MixedReality/tree/master/samples/BasicXrApp" target="_blank">BasicXrApp</a>示例应用。</span><span class="sxs-lookup"><span data-stu-id="08f6e-153">To see an example of the OpenXR API in action, check out the <a href="https://github.com/microsoft/OpenXR-MixedReality/tree/master/samples/BasicXrApp" target="_blank">BasicXrApp</a> sample app.</span></span>

### <a name="include-official-openxr-loader-source"></a><span data-ttu-id="08f6e-154">包括官方 OpenXR 加载程序源</span><span class="sxs-lookup"><span data-stu-id="08f6e-154">Include official OpenXR loader source</span></span>

<span data-ttu-id="08f6e-155">如果你想要自己生成加载程序，例如，避免出现额外的加载程序。DLL，则可以将官方 Khronos OpenXR 加载器源提取到项目中。</span><span class="sxs-lookup"><span data-stu-id="08f6e-155">If you want to build the loader yourself, for example to avoid the extra loader .DLL, you can pull the official Khronos OpenXR loader sources into your project.</span></span>  <span data-ttu-id="08f6e-156">这样，你就可以访问 OpenXR 1.0 核心功能，还可以访问发布的 `KHR``EXT` 和 `MSFT` 扩展。</span><span class="sxs-lookup"><span data-stu-id="08f6e-156">This will give you access to OpenXR 1.0 core features, plus published `KHR`, `EXT` and `MSFT` extensions.</span></span>

<span data-ttu-id="08f6e-157">若要开始操作，请按照<a href="https://github.com/KhronosGroup/OpenXR-SDK" target="_blank">GitHub 上的 Khronos OpenXR-SDK</a>存储库中的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="08f6e-157">To get started here, follow the instructions in the <a href="https://github.com/KhronosGroup/OpenXR-SDK" target="_blank">Khronos OpenXR-SDK repo on GitHub</a>.</span></span>  <span data-ttu-id="08f6e-158">项目设置为使用 CMake 进行生成-如果使用的是 MSBuild，则需要将代码复制到自己的项目中。</span><span class="sxs-lookup"><span data-stu-id="08f6e-158">The project is set up to build with CMake - if you are using MSBuild, you will need to copy to the code into your own project.</span></span>

## <a name="using-preview-extensions"></a><span data-ttu-id="08f6e-159">使用预览扩展</span><span class="sxs-lookup"><span data-stu-id="08f6e-159">Using preview extensions</span></span>

<span data-ttu-id="08f6e-160">[扩展路线图](openxr.md#roadmap)中列出的 `MSFT_preview` 扩展是为了收集反馈而预览的实验性供应商扩展。</span><span class="sxs-lookup"><span data-stu-id="08f6e-160">The `MSFT_preview` extensions listed in the [extension roadmap](openxr.md#roadmap) are experimental vendor extensions being previewed to gather feedback.</span></span>  <span data-ttu-id="08f6e-161">这些扩展仅适用于开发人员设备，并将在真正的扩展交付时删除。</span><span class="sxs-lookup"><span data-stu-id="08f6e-161">These extensions are for developer devices only and will be removed when the real extension ships.</span></span>

<span data-ttu-id="08f6e-162">如果你有兴趣试用可用的 `MSFT_preview` 扩展，请执行以下步骤以更新你的项目：</span><span class="sxs-lookup"><span data-stu-id="08f6e-162">If you're interested to try out the available `MSFT_preview` extensions, go through the following steps to update your project:</span></span>
1. <span data-ttu-id="08f6e-163">按照上述任一方法将 OpenXR 加载程序集成到项目中。</span><span class="sxs-lookup"><span data-stu-id="08f6e-163">Follow either of the approaches above to integrate an OpenXR loader into your project.</span></span>
1. <span data-ttu-id="08f6e-164">将项目中的标准 OpenXR 标头替换为<a href="https://github.com/microsoft/OpenXR-MixedReality/tree/master/openxr_preview/include/openxr" target="_blank">GitHub 上混合现实 OpenXR 存储库的预览标头</a>。</span><span class="sxs-lookup"><span data-stu-id="08f6e-164">Replace the standard OpenXR headers in your project with the <a href="https://github.com/microsoft/OpenXR-MixedReality/tree/master/openxr_preview/include/openxr" target="_blank">preview headers from the Mixed Reality OpenXR repo on GitHub</a>.</span></span>

<span data-ttu-id="08f6e-165">然后在目标 HoloLens 2 或台式计算机上激活预览扩展：</span><span class="sxs-lookup"><span data-stu-id="08f6e-165">To then activate preview extensions on your target HoloLens 2 or desktop PC:</span></span>
  1. <span data-ttu-id="08f6e-166">在目标设备上启用 Windows 设备门户：</span><span class="sxs-lookup"><span data-stu-id="08f6e-166">Enable Windows Device Portal on the target device:</span></span>
     * <span data-ttu-id="08f6e-167">如果目标设备是 HoloLens 2 设备，请按照目标设备上的[说明进行操作](using-the-windows-device-portal.md)。</span><span class="sxs-lookup"><span data-stu-id="08f6e-167">If your target device is a HoloLens 2 device, [follow these instructions](using-the-windows-device-portal.md) on the target device.</span></span>  <span data-ttu-id="08f6e-168">请注意，这需要物理耳机，因为 HoloLens 2 模拟器中的已知问题将阻止下一步中的 UI 出现在模拟器中。</span><span class="sxs-lookup"><span data-stu-id="08f6e-168">Note that this requires a physical headset, as a known issue in the HoloLens 2 emulator will prevent the UI in the next step from appearing in the emulator.</span></span>
     * <span data-ttu-id="08f6e-169">如果目标设备是连接了沉浸式耳机外设的台式计算机，请<a href="https://docs.microsoft.com/windows/uwp/debug-test-perf/device-portal-desktop#set-up-device-portal-on-windows-desktop" target="_blank">按照</a>目标台式计算机上的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="08f6e-169">If your target device is a desktop PC with an immersive headset peripheral attached, <a href="https://docs.microsoft.com/windows/uwp/debug-test-perf/device-portal-desktop#set-up-device-portal-on-windows-desktop" target="_blank">follow these instructions</a> on the target desktop PC.</span></span>
  1. <span data-ttu-id="08f6e-170">导航到左侧窗格中的 " **OpenXR** " 选项卡，并启用 "**使用最新预览版 OpenXR 运行时**"。</span><span class="sxs-lookup"><span data-stu-id="08f6e-170">Navigate to the **OpenXR** tab in the left pane and enable **Use latest preview OpenXR runtime**.</span></span>  <span data-ttu-id="08f6e-171">这将在你的设备上启用预览版扩展，并激活预览扩展。</span><span class="sxs-lookup"><span data-stu-id="08f6e-171">This enables the preview runtime on your device, which has preview extensions activated.</span></span>

<span data-ttu-id="08f6e-172">请参阅<a href="https://github.com/microsoft/OpenXR-MixedReality#openxr-preview-extensions" target="_blank">混合现实 OpenXR</a>存储库，以了解这些预览版扩展的文档以及如何使用它们的示例。</span><span class="sxs-lookup"><span data-stu-id="08f6e-172">See the <a href="https://github.com/microsoft/OpenXR-MixedReality#openxr-preview-extensions" target="_blank">Mixed Reality OpenXR repo</a> for documentation of these preview extensions and samples of how to use them.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="08f6e-173">故障排除</span><span class="sxs-lookup"><span data-stu-id="08f6e-173">Troubleshooting</span></span>

<span data-ttu-id="08f6e-174">如果在使用 OpenXR 开发时遇到问题，请查看[故障排除提示](openxr-troubleshooting.md)。</span><span class="sxs-lookup"><span data-stu-id="08f6e-174">If you have trouble getting up and running with OpenXR development, check out our [troubleshooting tips](openxr-troubleshooting.md).</span></span>