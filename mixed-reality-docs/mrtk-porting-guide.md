---
title: 让您的应用程序准备好使用 HoloLens 2
description: 面向开发人员在 HoloLens 上已有一个应用 （第 1 代） 和/或较旧 MRTK，并查找移植到 MRTK 版本 2 和 HoloLens 2。
author: author:grbury
ms.author: grbury
ms.date: 04/12/19
ms.topic: article
keywords: Windows Mixed Reality 测试，MRTK、 MRTK 版本 2、 HoloLens 2
ms.openlocfilehash: a5a329f69f5f9cc64666483adc92786ae8910b2f
ms.sourcegitcommit: 07773e094ace2e828e329bd55da759983be3b8c1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/15/2019
ms.locfileid: "59593105"
---
# <a name="getting-your-existing-app-ready-for-hololens-2"></a><span data-ttu-id="77f35-104">让您现有的应用程序准备好使用 HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="77f35-104">Getting your existing app ready for HoloLens 2</span></span>

<span data-ttu-id="77f35-105">本指南专门用于帮助开发人员有 HoloLens 1，端口为新的 HoloLens 2 设备应用程序的现有 Unity 应用。</span><span class="sxs-lookup"><span data-stu-id="77f35-105">This guide is specifically tailored to help developers who have an existing Unity app for HoloLens 1 to port their application for the new HoloLens 2 device.</span></span> <span data-ttu-id="77f35-106">有四个关键步骤 HoloLens 1 Unity 将应用移植到 HoloLens 2。</span><span class="sxs-lookup"><span data-stu-id="77f35-106">There are four key steps to porting a HoloLens 1 Unity app to HoloLens 2.</span></span> <span data-ttu-id="77f35-107">以下各节将详细介绍每个阶段的信息。</span><span class="sxs-lookup"><span data-stu-id="77f35-107">The sections below will detail information for each stage.</span></span> 

| <span data-ttu-id="77f35-108">步骤 1</span><span class="sxs-lookup"><span data-stu-id="77f35-108">Step 1</span></span> | <span data-ttu-id="77f35-109">步骤 2</span><span class="sxs-lookup"><span data-stu-id="77f35-109">Step 2</span></span> | <span data-ttu-id="77f35-110">步骤 3</span><span class="sxs-lookup"><span data-stu-id="77f35-110">Step 3</span></span> | <span data-ttu-id="77f35-111">步骤 4</span><span class="sxs-lookup"><span data-stu-id="77f35-111">Step 4</span></span> |
|----------|-------------------|-------------------|-------------------|
| ![Visual Studio 徽标](images/visualstudio_logo.png) | ![Unity 徽标](images/unity_logo.png)| ![Unity 图标](images/hololens2_icon.jpg) | ![MRTK 徽标](images/MRTKIcon.jpg) |
| <span data-ttu-id="77f35-116">下载最新的工具</span><span class="sxs-lookup"><span data-stu-id="77f35-116">Download latest tools</span></span> | <span data-ttu-id="77f35-117">更新 Unity 项目</span><span class="sxs-lookup"><span data-stu-id="77f35-117">Update Unity Project</span></span> | <span data-ttu-id="77f35-118">针对 ARM 编译</span><span class="sxs-lookup"><span data-stu-id="77f35-118">Compile for ARM</span></span> | <span data-ttu-id="77f35-119">将迁移到 MRTK v2</span><span class="sxs-lookup"><span data-stu-id="77f35-119">Migrate to MRTK v2</span></span>

<span data-ttu-id="77f35-120">它是**强烈建议**，才能开始迁移过程，开发人员利用源代码管理，以保存自己的应用程序的原始状态的快照。</span><span class="sxs-lookup"><span data-stu-id="77f35-120">It is **highly recommended** that, before beginning the porting process, developers utilize source control to save a snapshot of the original state of their app.</span></span> <span data-ttu-id="77f35-121">此外，建议向*保存*在过程中的不同位置的检查点状态。</span><span class="sxs-lookup"><span data-stu-id="77f35-121">Additionally, it is recommended to *save* checkpoint states at various points during the process.</span></span> <span data-ttu-id="77f35-122">它可以是非常有益的原始应用程序以在端口过程中用于通过并行比较的另一个 Unity 实例。</span><span class="sxs-lookup"><span data-stu-id="77f35-122">It can also be very helpful to have another Unity instance of the original app to allow for side-by-side comparison during the port process.</span></span> 

> [!NOTE]
> <span data-ttu-id="77f35-123">移植之前，请确保已安装用于 Windows Mixed Reality 开发最新工具。</span><span class="sxs-lookup"><span data-stu-id="77f35-123">Before porting, ensure you have the latest tools installed for Windows Mixed Reality development.</span></span> <span data-ttu-id="77f35-124">对于大多数现有的 HoloLens 开发人员，这将主要涉及更新到最新的 Visual Studio 2017 并安装相应的 Windows SDK。</span><span class="sxs-lookup"><span data-stu-id="77f35-124">For most existing HoloLens developers, this will primarily involve updating to the latest Visual Studio 2017 and installing the appropriate Windows SDK.</span></span> <span data-ttu-id="77f35-125">深入了解以下内容将进一步深入到不同的 Unity 版本和混合现实工具包版本 2。</span><span class="sxs-lookup"><span data-stu-id="77f35-125">The content below will dive further into different Unity versions and the Mixed Reality Toolkit version 2.</span></span>
>
> <span data-ttu-id="77f35-126">有关详细信息，请参阅[安装的工具](install-the-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="77f35-126">For more information, please see [Install the tools](install-the-tools.md).</span></span>

## <a name="migrate-project-to-latest-version-of-unity"></a><span data-ttu-id="77f35-127">将项目迁移到最新版本的 Unity</span><span class="sxs-lookup"><span data-stu-id="77f35-127">Migrate project to latest version of Unity</span></span>

<span data-ttu-id="77f35-128">移植您的 Unity 应用程序的第一步将在 Unity 的最新版本中打开它。</span><span class="sxs-lookup"><span data-stu-id="77f35-128">The first step to porting your Unity application will be to open it in the latest version of Unity.</span></span> <span data-ttu-id="77f35-129">目前，有两个选项可供选择：Unity 2018.3.x 或 Unity 2019.1.x beta。</span><span class="sxs-lookup"><span data-stu-id="77f35-129">Currently, there are two options to choose from: Unity 2018.3.x or Unity 2019.1.x beta.</span></span> <span data-ttu-id="77f35-130">有多个之间的权衡这两个版本，但基数的倍数的主要区别在于能够编译 ARM64 在 Unity 2019 及更高。</span><span class="sxs-lookup"><span data-stu-id="77f35-130">There are multiple trade-offs between these two versions but the primary difference of significance is the ability to compile for ARM64 in Unity 2019+.</span></span> 

<span data-ttu-id="77f35-131">开发人员应评估任何[插件依赖项](https://docs.unity3d.com/Manual/Plugins.html)，当前在其项目和是否可以针对 ARM64 生成这些 Dll 中存在。</span><span class="sxs-lookup"><span data-stu-id="77f35-131">Developers should assess any [plugin dependencies](https://docs.unity3d.com/Manual/Plugins.html) that currently exist in their project and whether or not these DLLs can be built for ARM64.</span></span> <span data-ttu-id="77f35-132">如果不能为 ARM64 生成硬依赖项插件，其中一个将需要利用 Unity 2018 LTS。</span><span class="sxs-lookup"><span data-stu-id="77f35-132">If a hard dependency plugin cannot be built for ARM64, then one will have to utilize Unity 2018 LTS.</span></span> <span data-ttu-id="77f35-133">移植到 ARM64 是通常所需的如果可能，因为有许多性能改进相比 ARM32 的设备上看到。</span><span class="sxs-lookup"><span data-stu-id="77f35-133">Porting to ARM64 is generally desired, if possible, as there are many performance improvements seen on device as compared to ARM32.</span></span>

<span data-ttu-id="77f35-134">此外，混合现实 Toolkit V2 将始终保证对 Unity 2018 LTS 的支持，但不是一定能保证对 Unity 2019.x+ 每次迭代的支持。</span><span class="sxs-lookup"><span data-stu-id="77f35-134">Further, the Mixed Reality Toolkit V2 will always guarantee support for Unity 2018 LTS but not necessarily guarantee support for every iteration of Unity 2019.x+.</span></span> 

| <span data-ttu-id="77f35-135">Unity 2018.3.x</span><span class="sxs-lookup"><span data-stu-id="77f35-135">Unity 2018.3.x</span></span> | <span data-ttu-id="77f35-136">Unity 2019.1 +</span><span class="sxs-lookup"><span data-stu-id="77f35-136">Unity 2019.1+</span></span> |
|----------|-------------------|
| <span data-ttu-id="77f35-137">ARM32 生成支持</span><span class="sxs-lookup"><span data-stu-id="77f35-137">ARM32 build support</span></span> | <span data-ttu-id="77f35-138">ARM32 和 ARM64 生成支持</span><span class="sxs-lookup"><span data-stu-id="77f35-138">ARM32 and ARM64 build support</span></span> |
| <span data-ttu-id="77f35-139">稳定 LTS 生成版本</span><span class="sxs-lookup"><span data-stu-id="77f35-139">Stable LTS build release</span></span> | <span data-ttu-id="77f35-140">Beta 稳定性</span><span class="sxs-lookup"><span data-stu-id="77f35-140">Beta stability</span></span> |
| <span data-ttu-id="77f35-141">[脚本编写的.NET 后端](https://docs.unity3d.com/Manual/windowsstore-dotnet.html)*不推荐使用*</span><span class="sxs-lookup"><span data-stu-id="77f35-141">[.NET Scripting back-end](https://docs.unity3d.com/Manual/windowsstore-dotnet.html) *deprecated*</span></span> | <span data-ttu-id="77f35-142">[脚本编写的.NET 后端](https://docs.unity3d.com/Manual/windowsstore-dotnet.html)*删除*</span><span class="sxs-lookup"><span data-stu-id="77f35-142">[.NET Scripting back-end](https://docs.unity3d.com/Manual/windowsstore-dotnet.html) *removed*</span></span> |
| <span data-ttu-id="77f35-143">UNET 网络*不推荐使用*</span><span class="sxs-lookup"><span data-stu-id="77f35-143">UNET Networking *deprecated*</span></span> | <span data-ttu-id="77f35-144">UNET 网络*删除*</span><span class="sxs-lookup"><span data-stu-id="77f35-144">UNET Networking *removed*</span></span> |

## <a name="update-sceneproject-settings-in-unity"></a><span data-ttu-id="77f35-145">更新 Unity 中的场景/项目设置</span><span class="sxs-lookup"><span data-stu-id="77f35-145">Update scene/project settings in Unity</span></span>

<span data-ttu-id="77f35-146">更新了对 Unity 之后 2018.3.x 或 Unity 2019 + 中，建议更新在 Unity 中的设备上获得最佳结果的特定设置。</span><span class="sxs-lookup"><span data-stu-id="77f35-146">After updating to Unity 2018.3.x or Unity 2019+, it is recommended to update particular settings in Unity for optimal results on device.</span></span> <span data-ttu-id="77f35-147">这些设置下的详细信息中所述**[推荐设置为 Unity](Recommended-settings-for-Unity.md)**。</span><span class="sxs-lookup"><span data-stu-id="77f35-147">These settings are outlined in detail under **[Recommended settings for Unity](Recommended-settings-for-Unity.md)**.</span></span>

<span data-ttu-id="77f35-148">应重新进行循环访问的[.NET 脚本的后端](https://docs.unity3d.com/Manual/windowsstore-dotnet.html)在 Unity 2018 中弃用并*删除*中 Unity 2019，因此，开发人员应考虑其项目切换到[IL2CPP](https://docs.unity3d.com/Manual/IL2CPP.html)。</span><span class="sxs-lookup"><span data-stu-id="77f35-148">It should be re-iterated that the [.NET Scripting back-end](https://docs.unity3d.com/Manual/windowsstore-dotnet.html) is being deprecated in Unity 2018 and *removed* in Unity 2019 and thus, developers should strongly consider switching their project over to [IL2CPP](https://docs.unity3d.com/Manual/IL2CPP.html).</span></span> 

> [!NOTE]
> <span data-ttu-id="77f35-149">IL2CPP 脚本编写后端可以到 Visual Studio 从 Unity 导致生成时间较长，因此开发人员应设置为其开发人员计算机[优化 IL2CPP 生成时间](https://docs.unity3d.com/Manual/IL2CPP-OptimizingBuildTimes.html)。</span><span class="sxs-lookup"><span data-stu-id="77f35-149">IL2CPP scripting back-end can cause longer build times from Unity to Visual Studio and thus developers should setup their developer machine for [optimizing IL2CPP build times](https://docs.unity3d.com/Manual/IL2CPP-OptimizingBuildTimes.html).</span></span>

<span data-ttu-id="77f35-150">之后在迁移到更新的 Unity 版本后寻址任何重大更改，开发人员应生成和测试在 HoloLens 上的其当前应用程序 （第 1 代）。</span><span class="sxs-lookup"><span data-stu-id="77f35-150">After addressing any breaking changes after moving to the updated Unity version, developers should build and test their current apps on HoloLens (1st gen).</span></span> <span data-ttu-id="77f35-151">此外，这是很好的点来创建和保存源代码管理的提交。</span><span class="sxs-lookup"><span data-stu-id="77f35-151">Further, this is a good point to create and save a commit for source control.</span></span> 

## <a name="compile-dependenciesplugins-for-arm-processor"></a><span data-ttu-id="77f35-152">编译为 ARM 处理器的依赖项/插件</span><span class="sxs-lookup"><span data-stu-id="77f35-152">Compile dependencies/plugins for ARM processor</span></span>

<span data-ttu-id="77f35-153">HoloLens （第 1 代） 在 x86 上执行应用程序时新 HoloLens 2 设备利用 ARM 处理器的处理器。</span><span class="sxs-lookup"><span data-stu-id="77f35-153">HoloLens (1st gen) executed applications on an x86 processor while the new HoloLens 2 device utilizes an ARM processor.</span></span> <span data-ttu-id="77f35-154">因此，现有的应用程序需要通过移植以支持 ARM。</span><span class="sxs-lookup"><span data-stu-id="77f35-154">Thus, existing applications need to be ported over to support ARM.</span></span> <span data-ttu-id="77f35-155">如前文所述，Unity 2018 支持 Unity 2019 + 支持 ARM64 应用的编译时 ARM32 应用的编译。</span><span class="sxs-lookup"><span data-stu-id="77f35-155">As noted earlier, Unity 2018 supports compiling for ARM32 apps while Unity 2019+ supports compiling for ARM64 apps.</span></span> <span data-ttu-id="77f35-156">用于 ARM64 的应用程序开发是通常首选，因为性能存在重大差异。</span><span class="sxs-lookup"><span data-stu-id="77f35-156">Developing for ARM64 applications is generally preferred as there is a material difference in performance.</span></span> <span data-ttu-id="77f35-157">但是，这需要所有[插件依赖项](https://docs.unity3d.com/Manual/Plugins.html)还生成用于 ARM64。</span><span class="sxs-lookup"><span data-stu-id="77f35-157">However, this requires all [plugin dependencies](https://docs.unity3d.com/Manual/Plugins.html) to also be built for ARM64.</span></span> 

<span data-ttu-id="77f35-158">当前查看应用程序中的所有 DLL 依赖项。</span><span class="sxs-lookup"><span data-stu-id="77f35-158">Review all DLL dependencies in your application currently.</span></span> <span data-ttu-id="77f35-159">如果不再需要依赖项，则最好从项目中删除它。</span><span class="sxs-lookup"><span data-stu-id="77f35-159">If a dependency is no longer needed, it is advisable to remove it from your project.</span></span> <span data-ttu-id="77f35-160">为所需的剩余插件，向你的 Unity 项目中引入各自 ARM32 或 ARM64 二进制文件。</span><span class="sxs-lookup"><span data-stu-id="77f35-160">For remaining plugins that are required, ingest the respective ARM32 or ARM64 binaries into your Unity project.</span></span> 

<span data-ttu-id="77f35-161">之后引入相关的 Dll 中的 Unity 生成的 Visual Studio 解决方案，然后编译 Visual Studio 来测试可以针对 ARM 处理器生成你的应用程序中的 ARM AppX。</span><span class="sxs-lookup"><span data-stu-id="77f35-161">After ingesting the relevant DLLs, build a Visual Studio solution from Unity and then compile an AppX for ARM in Visual Studio to test that your application can be built for ARM processors.</span></span> <span data-ttu-id="77f35-162">它建议将保存在源代码管理解决方案中的提交此另一个点。</span><span class="sxs-lookup"><span data-stu-id="77f35-162">This another point where it is advised to save a commit in your source control solution.</span></span> 

## <a name="update-to-mrtk-version-2"></a><span data-ttu-id="77f35-163">更新到 MRTK 版本 2</span><span class="sxs-lookup"><span data-stu-id="77f35-163">Update to MRTK version 2</span></span>

<span data-ttu-id="77f35-164">MRTK 版本 2 是基于 Unity 支持这两个 HoloLens 的新工具包 （第 1 代） 和 HoloLens 2 和其中的所有新的 HoloLens 2 功能已添加，如将交互，并眼睛跟踪。</span><span class="sxs-lookup"><span data-stu-id="77f35-164">MRTK version 2 is the new toolkit on top of Unity supporting both HoloLens (1st gen) and HoloLens 2, and where all of the new HoloLens 2 capabilities have been added, such as hand interactions and eye tracking.</span></span>

### <a name="prepare-for-the-migration"></a><span data-ttu-id="77f35-165">为迁移准备</span><span class="sxs-lookup"><span data-stu-id="77f35-165">Prepare for the migration</span></span>

<span data-ttu-id="77f35-166">之前引入的新[\*.unitypackage 文件 MRTK v2](https://github.com/Microsoft/MixedRealityToolkit-Unity/releases)，建议清点**MRTK v1 与集成，1） 任何自定义生成代码**和**2） 任何自定义生成代码为输入的交互或 UX 组件**。</span><span class="sxs-lookup"><span data-stu-id="77f35-166">Before ingesting the new [\*.unitypackage files for MRTK v2](https://github.com/Microsoft/MixedRealityToolkit-Unity/releases), it is recommended to take an inventory of **1) any custom-built code that integrates with MRTK v1** and **2) any custom-built code for input interactions or UX components**.</span></span> <span data-ttu-id="77f35-167">最常见和流行，以致 Mixed Reality 开发人员引入新 MRTK v2 冲突将涉及输入和交互。</span><span class="sxs-lookup"><span data-stu-id="77f35-167">The most common and prevalent conflict for a Mixed Reality developer ingesting the new MRTK v2 will involve input and interactions.</span></span> <span data-ttu-id="77f35-168">因此，建议在开始阅读和理解[MRTK v2 输入的模型](https://microsoft.github.io/MixedRealityToolkit-Unity/Documentation/Input/Overview.html)。</span><span class="sxs-lookup"><span data-stu-id="77f35-168">Thus, it is advised to begin reading and understanding the [MRTK v2 input model](https://microsoft.github.io/MixedRealityToolkit-Unity/Documentation/Input/Overview.html).</span></span>

<span data-ttu-id="77f35-169">最后，新 MRTK v2 已从脚本和场景中管理器对象模型转换到的配置和服务提供程序体系结构。</span><span class="sxs-lookup"><span data-stu-id="77f35-169">Finally, the new MRTK v2 has transitioned from a model of scripts and in-scene manager objects to a configuration and services provider architecture.</span></span> <span data-ttu-id="77f35-170">这将导致更简洁的场景层次结构和体系结构模型，但对于了解新的配置文件需要一个学习曲线。</span><span class="sxs-lookup"><span data-stu-id="77f35-170">This results in a cleaner scene hierarchy and architecture model but requires a learning curve for understanding the new configuration profiles.</span></span> <span data-ttu-id="77f35-171">因此，请阅读[混合现实工具包配置指南](https://microsoft.github.io/MixedRealityToolkit-Unity/Documentation/MixedRealityConfigurationGuide.html)以开始熟悉重要的设置和配置文件，以适应你的应用程序的需求。</span><span class="sxs-lookup"><span data-stu-id="77f35-171">Thus, please read the [Mixed Reality Toolkit Configuration Guide](https://microsoft.github.io/MixedRealityToolkit-Unity/Documentation/MixedRealityConfigurationGuide.html) to start becoming familiar with the important settings and profiles to adjust to the needs of your application.</span></span> 

### <a name="perform-the-migration"></a><span data-ttu-id="77f35-172">执行迁移</span><span class="sxs-lookup"><span data-stu-id="77f35-172">Perform the migration</span></span>

<span data-ttu-id="77f35-173">导入后 MRTK v2，Unity 项目将可能有许多与编译器相关的错误。</span><span class="sxs-lookup"><span data-stu-id="77f35-173">After importing MRTK v2, your Unity project will likely have many compiler related errors.</span></span> <span data-ttu-id="77f35-174">这通常是由于新命名空间的结构和新组件名称。</span><span class="sxs-lookup"><span data-stu-id="77f35-174">These are most commonly due to the new namespace structure and new component names.</span></span> <span data-ttu-id="77f35-175">继续通过修改你对新的命名空间和组件的脚本来纠正这些错误。</span><span class="sxs-lookup"><span data-stu-id="77f35-175">Proceed to resolve these errors by modifying your scripts to the new namespaces and components.</span></span> 

<span data-ttu-id="77f35-176">HTK/MRTK 和 MRTK 版本 2 之间的特定 API 差异的详细信息，请参阅迁移指南上[MRTK 版本 2 wiki](https://microsoft.github.io/MixedRealityToolkit-Unity/Documentation/HTKToMRTKPortingGuide.html)。</span><span class="sxs-lookup"><span data-stu-id="77f35-176">For more information on specific API differences between HTK/MRTK and MRTK version 2, see the porting guide on the [MRTK Version 2 wiki](https://microsoft.github.io/MixedRealityToolkit-Unity/Documentation/HTKToMRTKPortingGuide.html).</span></span>

### <a name="best-practices"></a><span data-ttu-id="77f35-177">最佳做法</span><span class="sxs-lookup"><span data-stu-id="77f35-177">Best practices</span></span>

- <span data-ttu-id="77f35-178">更喜欢使用 MRTK 标准着色器</span><span class="sxs-lookup"><span data-stu-id="77f35-178">Prefer use of the MRTK Standard shader</span></span>
- <span data-ttu-id="77f35-179">上一个重大工作一次更改类型 (例如：到 IMixedRealityFocusHandler IFocusable)</span><span class="sxs-lookup"><span data-stu-id="77f35-179">Work on one breaking change type at a time (ex: IFocusable to IMixedRealityFocusHandler)</span></span>
- <span data-ttu-id="77f35-180">每次更改后测试并使用源代码管理</span><span class="sxs-lookup"><span data-stu-id="77f35-180">Test after every change and utilize source control</span></span>
- <span data-ttu-id="77f35-181">使用默认的 MRTK UX （按钮、 平板电脑等） 在可能的情况</span><span class="sxs-lookup"><span data-stu-id="77f35-181">Use default MRTK UX (buttons, slates, etc) when possible</span></span>
- <span data-ttu-id="77f35-182">尝试避免直接修改 MRTK 文件，请改为创建包装 MRTK 组件</span><span class="sxs-lookup"><span data-stu-id="77f35-182">Try to refrain from modifying MRTK files directly, instead create wrappers around MRTK components</span></span>
    - <span data-ttu-id="77f35-183">这将防止将来 MRTK ingestions 和更新</span><span class="sxs-lookup"><span data-stu-id="77f35-183">This will protect against future MRTK ingestions and updates</span></span>
- <span data-ttu-id="77f35-184">查看和探索 MRTK 中提供的示例场景 (尤其是*HandInteractionExamples.scene*)</span><span class="sxs-lookup"><span data-stu-id="77f35-184">Review & explore sample scenes provided in MRTK (especially *HandInteractionExamples.scene*)</span></span>
- <span data-ttu-id="77f35-185">而是重新生成基于画布的 UI 与四边形、 碰撞体和 TextMeshPro 文本</span><span class="sxs-lookup"><span data-stu-id="77f35-185">Rebuild canvas-based UI with quads, colliders and TextMeshPro text instead</span></span>

### <a name="testing-your-application"></a><span data-ttu-id="77f35-186">测试应用程序</span><span class="sxs-lookup"><span data-stu-id="77f35-186">Testing your application</span></span>

<span data-ttu-id="77f35-187">现在，MRTK 版本 2 中提供了 HoloLens 2 组件和功能在[RC1](https://github.com/Microsoft/MixedRealityToolkit-Unity/releases/tag/v2.0.0-RC1)，可以模拟直接在 Unity 中，手动交互，并针对用于手动交互和的眼跟踪的新 Api 进行开发。</span><span class="sxs-lookup"><span data-stu-id="77f35-187">Now that HoloLens 2 components and capabilities are available in MRTK version 2, as of [RC1](https://github.com/Microsoft/MixedRealityToolkit-Unity/releases/tag/v2.0.0-RC1), you can simulate the hand interactions directly in Unity, and develop against the new APIs for hand interactions and eye tracking.</span></span>  <span data-ttu-id="77f35-188">HoloLens 2 设备需要创建更完美的体验，但至少一个可以开始学习工具和文档中。</span><span class="sxs-lookup"><span data-stu-id="77f35-188">The HoloLens 2 device is required to create a great experience, but at least one could start learning in the tools and documentation.</span></span> <span data-ttu-id="77f35-189">此外，MRTK v2 支持在 HoloLens 上开发 （第 1 代） 和传统输入因此，模型如通过敲击选择仍在 HoloLens 上测试 （第 1 代） 设备。</span><span class="sxs-lookup"><span data-stu-id="77f35-189">Further, MRTK v2 supports development on HoloLens (1st gen) and thus, traditional input models such as select via air-tap can still be tested on HoloLens (1st gen) devices.</span></span> 

## <a name="updating-interaction-model-for-hololens-2"></a><span data-ttu-id="77f35-190">HoloLens 2 更新交互模型</span><span class="sxs-lookup"><span data-stu-id="77f35-190">Updating interaction model for HoloLens 2</span></span>

<span data-ttu-id="77f35-191">在应用程序移植并准备好 HoloLens 2 后，你现可考虑更新您的交互模型和全息图设计/的位置。</span><span class="sxs-lookup"><span data-stu-id="77f35-191">Once you have your app ported and prepped for HoloLens 2, you are ready to consider updating your interaction model and hologram designs/placement.</span></span>
<span data-ttu-id="77f35-192">来自 HoloLens （第 1 代），应用可能具有的视线移动并提交交互模型，与全息相对较远而无法放入视图的字段。</span><span class="sxs-lookup"><span data-stu-id="77f35-192">Coming from HoloLens (1st gen), your app likely has a gaze and commit interaction model, with holograms relatively far away to fit into the field of view.</span></span>

<span data-ttu-id="77f35-193">若要更新您的应用程序设计为最适合 HoloLens 2 的步骤：</span><span class="sxs-lookup"><span data-stu-id="77f35-193">Steps to update your app design to be best for HoloLens 2:</span></span>
1.  <span data-ttu-id="77f35-194">MRTK 组件：每个预工作，如果添加 MRTK v2，有各种组件/利用的脚本已进行了设计和优化 HoloLens 2。</span><span class="sxs-lookup"><span data-stu-id="77f35-194">MRTK components: Per the pre-work, if you added MRTK v2, there are various components/scripts to leverage that have been designed and optimized for HoloLens 2.</span></span>

2.  <span data-ttu-id="77f35-195">交互模型：请考虑更新您的交互模型。</span><span class="sxs-lookup"><span data-stu-id="77f35-195">Interaction model: Consider updating your interaction model.</span></span>  <span data-ttu-id="77f35-196">大多数情况下，我们建议从注视切换并提交到手中。</span><span class="sxs-lookup"><span data-stu-id="77f35-196">For most scenarios, we recommend switching from gaze and commit to hands.</span></span>  <span data-ttu-id="77f35-197">使用你通常要超出手臂达到的全息，切换到手将导致最交互指针大气并获取手势。</span><span class="sxs-lookup"><span data-stu-id="77f35-197">With your holograms typically being out of arms reach, switching to hands will result in far interaction pointing rays and grab gestures.</span></span>
<span data-ttu-id="77f35-198">注意： 在无需手动交互模型是必需的如任务工作线程持有工具，并且没有这种情况下的特定设计指南的情况下。</span><span class="sxs-lookup"><span data-stu-id="77f35-198">Note: there are scenarios where a hands-free interaction model is required, such as a task worker holding tools, and there is specific design guidance for such cases.</span></span> 

3.  <span data-ttu-id="77f35-199">全息图放置：后切换到手交互模型，请考虑更接近移动某些全息与用手，使用附近交互随取即行手势全息直接交互。</span><span class="sxs-lookup"><span data-stu-id="77f35-199">Hologram placement: After switching to a hands interaction model, consider moving some holograms closer to directly interact with the holograms with your hands, using near interaction grab gestures.</span></span>  <span data-ttu-id="77f35-200">全息建议更接近直接获取，或进行交互的类型是较小的目标菜单、 控件、 按钮和较小全息适合 HoloLens 2 视图的字段时捕获并检查全息图。</span><span class="sxs-lookup"><span data-stu-id="77f35-200">The types of holograms recommended to move closer to directly grab or interact are small target menus, controls, buttons, and smaller holograms that fit within the HoloLens 2 field of view when grabbing and inspecting the hologram.</span></span>
<br>
<span data-ttu-id="77f35-201">每个应用程序和方案都不同，并且我们将继续进行优化和发布帖子设计指南的反馈基础并继续了解的情况。</span><span class="sxs-lookup"><span data-stu-id="77f35-201">Every app and scenario is different, and we’ll continue to refine and post design guidance based on feedback and continued learnings.</span></span>


## <a name="additional-learnings-from-moving-apps-from-x86-to-arm"></a><span data-ttu-id="77f35-202">从应用程序从 x86 移动到 ARM 的更多知识</span><span class="sxs-lookup"><span data-stu-id="77f35-202">Additional learnings from moving apps from x86 to ARM</span></span>

- <span data-ttu-id="77f35-203">可以生成一个 ARM appx 捆绑包，也可以直接向设备部署并运行它，直接 Unity 应用非常简单。</span><span class="sxs-lookup"><span data-stu-id="77f35-203">Straight Unity apps are simple as you can build an ARM appx bundle or deploy directly to the device and it runs.</span></span>
<span data-ttu-id="77f35-204">Unity 应用程序使用本机插件时，面临的挑战。</span><span class="sxs-lookup"><span data-stu-id="77f35-204">The challenge comes when the Unity app uses native plugins.</span></span>  <span data-ttu-id="77f35-205">所有本机插件需要升级到 VS2017 和重新生成对于 ARM，以及 Unity 2019，ARM64。</span><span class="sxs-lookup"><span data-stu-id="77f35-205">All of the native plugins need to be upgraded to VS2017 and rebuilt for ARM, and with Unity 2019, ARM64.</span></span>

- <span data-ttu-id="77f35-206">一个应用，用于 Unity，AudioKinetic Wwise 插件，所使用的版本没有 UWP ARM 插件。</span><span class="sxs-lookup"><span data-stu-id="77f35-206">One app, used the AudioKinetic Wwise plugin for Unity, and the version used didn’t have a UWP ARM plugin.</span></span> <span data-ttu-id="77f35-207">花费几天时间才能重新使用应用程序用于 ARM 的声音。</span><span class="sxs-lookup"><span data-stu-id="77f35-207">It took several days to re-work the sound in the application to work on ARM.</span></span>

- <span data-ttu-id="77f35-208">在其他情况下，UWP/ARM 插件可能不存在的应用程序所需的插件、 端口和 HoloLens 2 上运行的能力造成了阻碍。</span><span class="sxs-lookup"><span data-stu-id="77f35-208">In other cases, a UWP/ARM plugin may not exist for app-required plugins, blocking the ability to port and run on HoloLens 2.</span></span>  <span data-ttu-id="77f35-209">可能需要插件提供商合作，以取消阻止，支持 ARM。</span><span class="sxs-lookup"><span data-stu-id="77f35-209">Engagement with the plugin provider may be needed to unblock and support ARM.</span></span>

- <span data-ttu-id="77f35-210">在着色器 minfloat （和变量，例如 min16float、 minint、 等） 的行为可能有所不同 HoloLen 2 比在 HoloLens 上 （第 1 代）。</span><span class="sxs-lookup"><span data-stu-id="77f35-210">The minfloat (and variants such as min16float, minint, etc…) in shaders may behave differently on HoloLen 2 than on HoloLens (1st gen).</span></span> <span data-ttu-id="77f35-211">具体而言，这些保证"至少指定将使用比特数"。</span><span class="sxs-lookup"><span data-stu-id="77f35-211">Specifically, these guarantee that “at least the specified number of bits will be used”.</span></span> <span data-ttu-id="77f35-212">Intel/Nvidia Gpu 上这些很大程度上就被视为 32 位。</span><span class="sxs-lookup"><span data-stu-id="77f35-212">On Intel/Nvidia GPUs, these are largely just treated as 32 bits.</span></span> <span data-ttu-id="77f35-213">在 ARM，实际上遵循指定的位数。</span><span class="sxs-lookup"><span data-stu-id="77f35-213">On ARM, the number of bits specified is actually respected.</span></span> <span data-ttu-id="77f35-214">这意味着，在实践中，这些数字可能具有较少精度/范围 HoloLens 2 上与在 HoloLens 上 （第 1 代）。</span><span class="sxs-lookup"><span data-stu-id="77f35-214">That means that in practice, these numbers may have less precision/range on HoloLens 2 than they did on HoloLens (1st gen).</span></span>

- <span data-ttu-id="77f35-215">_Asm 说明不会显示用于 ARM，这意味着使用 _asm 说明的任何代码必须重写。</span><span class="sxs-lookup"><span data-stu-id="77f35-215">The _asm instructions don’t appear to work on ARM, meaning any code using _asm instructions will have to be rewritten.</span></span>

- <span data-ttu-id="77f35-216">ARM 不支持 SIMD 指令集。</span><span class="sxs-lookup"><span data-stu-id="77f35-216">The SIMD instruction set is not supported on ARM.</span></span> <span data-ttu-id="77f35-217">这意味着各种标头，例如 xmmintrin.h、 emmintrin.h、 tmmintrin.h 和 immintrin.h 不是在 ARM 上可用。</span><span class="sxs-lookup"><span data-stu-id="77f35-217">This means various headers, such as xmmintrin.h, emmintrin.h, tmmintrin.h, and immintrin.h are not available on ARM.</span></span>

- <span data-ttu-id="77f35-218">着色器编译器在 ARM 运行时期间的第一个绘图调用后的着色器已加载或着色器的内容依赖于已更改，不是在着色器加载时间。</span><span class="sxs-lookup"><span data-stu-id="77f35-218">The shader compiler on ARM runs during the first draw call after the shader has been loaded or something the shader relies on has changed, not at shader load time.</span></span> <span data-ttu-id="77f35-219">对帧速率的影响可以是非常明显，具体取决于多少着色器需要进行编译。</span><span class="sxs-lookup"><span data-stu-id="77f35-219">The impact on framerate can be very noticeable, depending on how many shaders need to be compiled.</span></span> <span data-ttu-id="77f35-220">这有不同的含义的着色器应如何处理/打包/更新以不同的方式上 HoloLens 2 vs HoloLens （第 1 代）。</span><span class="sxs-lookup"><span data-stu-id="77f35-220">This has various implications for how shaders should be handled/packaged/updated differently on HoloLens 2 vs HoloLens (1st gen).</span></span>

## <a name="see-also"></a><span data-ttu-id="77f35-221">请参阅</span><span class="sxs-lookup"><span data-stu-id="77f35-221">See also</span></span>
* [<span data-ttu-id="77f35-222">开始使用 MRTK 版本 2</span><span class="sxs-lookup"><span data-stu-id="77f35-222">Getting started with MRTK version 2</span></span>](mrtk-getting-started.md)
* [<span data-ttu-id="77f35-223">MRTK 版本 2 操作方法</span><span class="sxs-lookup"><span data-stu-id="77f35-223">MRTK Version 2 HowTo</span></span>](https://microsoft.github.io/MixedRealityToolkit-Unity/External/HowTo/README.html)
* [<span data-ttu-id="77f35-224">安装工具</span><span class="sxs-lookup"><span data-stu-id="77f35-224">Install the tools</span></span>](install-the-tools.md)
* [<span data-ttu-id="77f35-225">Unity 的推荐的设置</span><span class="sxs-lookup"><span data-stu-id="77f35-225">Recommended settings for Unity</span></span>](recommended-settings-for-unity.md)
* [<span data-ttu-id="77f35-226">混合现实的了解性能</span><span class="sxs-lookup"><span data-stu-id="77f35-226">Understanding performance for Mixed Reality</span></span>](understanding-performance-for-mixed-reality.md)
