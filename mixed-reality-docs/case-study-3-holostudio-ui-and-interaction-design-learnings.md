---
title: 案例研究-3 HoloStudio UI 和交互设计知识
description: HoloStudio UI 和交互设计经验
author: rwinj
ms.author: marcghal
ms.date: 03/21/2018
ms.topic: article
keywords: HoloLens，HoloStudio，Windows 混合现实
ms.openlocfilehash: 217c489fed3c0588dae1c2753db6ba15da3522c8
ms.sourcegitcommit: 384b0087899cd835a3a965f75c6f6c607c9edd1b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/12/2019
ms.locfileid: "59592639"
---
# <a name="case-study---3-holostudio-ui-and-interaction-design-learnings"></a><span data-ttu-id="55771-104">案例研究-3 HoloStudio UI 和交互设计知识</span><span class="sxs-lookup"><span data-stu-id="55771-104">Case study - 3 HoloStudio UI and interaction design learnings</span></span>

<span data-ttu-id="55771-105">[HoloStudio](https://www.youtube.com/watch?v=BRIJG0x_We8) HoloLens 的是第一个 Microsoft 应用程序之一。</span><span class="sxs-lookup"><span data-stu-id="55771-105">[HoloStudio](https://www.youtube.com/watch?v=BRIJG0x_We8) was one of the first Microsoft apps for HoloLens.</span></span> <span data-ttu-id="55771-106">因此，我们需要创建新 3d UI 的最佳做法和交互设计。</span><span class="sxs-lookup"><span data-stu-id="55771-106">Because of this, we had to create new best practices for 3D UI and interaction design.</span></span> <span data-ttu-id="55771-107">我们通过大量的用户测试、 原型制作和试用和错误。</span><span class="sxs-lookup"><span data-stu-id="55771-107">We did this through a lot of user testing, prototyping, and trial and error.</span></span>

<span data-ttu-id="55771-108">我们知道，并非每个人都具有其可供使用，来进行研究此类的资源，因此，我们必须我们高级全息版的设计器，Marcus Ghaly 共享三件事我们了解到有关 HoloLens 应用的 UI 和交互设计 HoloStudio 开发的过程。</span><span class="sxs-lookup"><span data-stu-id="55771-108">We know that not everyone has the resources at their disposal to do this type of research, so we had our Sr. Holographic Designer, Marcus Ghaly, share three things we learned during the development of HoloStudio about UI and interaction design for HoloLens apps.</span></span>

## <a name="watch-the-video"></a><span data-ttu-id="55771-109">观看视频</span><span class="sxs-lookup"><span data-stu-id="55771-109">Watch the video</span></span>

>[!VIDEO https://www.youtube.com/embed/sX6yKHmN1qM]

## <a name="problem-1-people-didnt-want-to-move-around-their-creations"></a><span data-ttu-id="55771-110">问题 #1:用户不想要移动其作品</span><span class="sxs-lookup"><span data-stu-id="55771-110">Problem #1: People didn't want to move around their creations</span></span>

<span data-ttu-id="55771-111">我们最初设计中 HoloStudio workbench 为一个矩形，更像你会发现现实世界中。</span><span class="sxs-lookup"><span data-stu-id="55771-111">We originally designed the workbench in HoloStudio as a rectangle, much like you'd find in the real world.</span></span> <span data-ttu-id="55771-112">问题在于人们的体验，告知他们继续仍时它们坐在桌旁或工作计算机前状态，以便它们并不移动围绕在 workbench 并从所有边探索其 3D 创建的生存期。</span><span class="sxs-lookup"><span data-stu-id="55771-112">The problem is that people have a lifetime of experience that tells them to stay still when they're sitting at a desk or working in front of a computer, so they weren't moving around the workbench and exploring their 3D creation from all sides.</span></span>

![在 workbench 中 HoloStudio 矩形设计 dissuaded 中四处移动，并查看所有边从其创建的用户。](images/rectangular-workbench-500px.jpg)

<span data-ttu-id="55771-114">我们的见解，以使 workbench 舍入，以便没有任何"前端"或清除已假定以突出显示的位置。</span><span class="sxs-lookup"><span data-stu-id="55771-114">We had the insight to make the workbench round, so that there was no "front" or clear place that you were supposed to stand.</span></span> <span data-ttu-id="55771-115">当我们测试表明时，突然人开始四处移动和其自己探索其作品。</span><span class="sxs-lookup"><span data-stu-id="55771-115">When we tested this, suddenly people started moving around and exploring their creations on their own.</span></span>

![循环 workbench 设计鼓励用户一直四处其作品。](images/circular-workbench-500px.jpg)

<span data-ttu-id="55771-117">**我们了解到的内容**</span><span class="sxs-lookup"><span data-stu-id="55771-117">**What we learned**</span></span>

<span data-ttu-id="55771-118">始终为思考一下什么是熟练的用户。</span><span class="sxs-lookup"><span data-stu-id="55771-118">Always be thinking about what's comfortable for the user.</span></span> <span data-ttu-id="55771-119">充分利用其物理空间是 HoloLens 和不能与其他设备做的事情很酷的功能。</span><span class="sxs-lookup"><span data-stu-id="55771-119">Taking advantage of their physical space is a cool feature of HoloLens and something you can't do with other devices.</span></span>

## <a name="problem-2-modal-dialogs-are-sometimes-out-of-the-holographic-frame"></a><span data-ttu-id="55771-120">问题 #2:模式对话框有时不 holographic 帧</span><span class="sxs-lookup"><span data-stu-id="55771-120">Problem #2: Modal dialogs are sometimes out of the holographic frame</span></span>

<span data-ttu-id="55771-121">有时，可能需要其关注应用程序中的不同方向从某些对象中查找你的用户。</span><span class="sxs-lookup"><span data-stu-id="55771-121">Sometimes, your user may be looking in a different direction from something that needs their attention in your app.</span></span> <span data-ttu-id="55771-122">在 PC 上，只是弹出可以启动一个对话框，但如果某人的人脸在 3D 环境中执行此操作，它可以感觉对话框获取按自己的方式。</span><span class="sxs-lookup"><span data-stu-id="55771-122">On a PC, you can just pop up a dialog, but if you do this in someone's face in a 3D environment, it can feel like the dialog is getting in their way.</span></span> <span data-ttu-id="55771-123">你需要它们以读取消息，但其想到的是尝试摆脱它。</span><span class="sxs-lookup"><span data-stu-id="55771-123">You need them to read the message, but their instinct is to try to get away from it.</span></span> <span data-ttu-id="55771-124">如果您正在玩游戏，但在设计工作的一种工具，它是不太理想，这种反应是很好。</span><span class="sxs-lookup"><span data-stu-id="55771-124">This reaction is great if you're playing a game, but in a tool designed for work, it's less than ideal.</span></span>

<span data-ttu-id="55771-125">之后尝试几个不同的事物，我们最后决定使用我们的对话框的"认为气泡"系统和添加 tendrils，用户可以通过到我们的应用程序中需要其关注的位置。</span><span class="sxs-lookup"><span data-stu-id="55771-125">After trying a few different things, we finally settled on using a "thought bubble" system for our dialogs and added tendrils that users can follow to where their attention is needed in our application.</span></span> <span data-ttu-id="55771-126">我们还进行隐式的方向性的意义上，以便用户知道到哪儿去 tendrils pulse。</span><span class="sxs-lookup"><span data-stu-id="55771-126">We also made the tendrils pulse, which implied a sense of directionality so that users knew where to go.</span></span>

!["认为气泡"系统包含闪烁 tendrils 提供某种意义上的方向，从而导致其关注其中需要在应用中的用户。](images/thought-bubble-500px.jpg)

<span data-ttu-id="55771-128">**我们了解到的内容**</span><span class="sxs-lookup"><span data-stu-id="55771-128">**What we learned**</span></span>

<span data-ttu-id="55771-129">会在 3D 中的内容所需的要多加注意，警告用户非常困难。</span><span class="sxs-lookup"><span data-stu-id="55771-129">It's much harder in 3D to alert users to things they need to pay attention to.</span></span> <span data-ttu-id="55771-130">如使用关注主管[空间声音](spatial-sound.md)、 浅色大气，或考虑冒泡，可能会导致用户他们需要为。</span><span class="sxs-lookup"><span data-stu-id="55771-130">Using attention directors such as [spatial sound](spatial-sound.md), light rays, or thought bubbles, can lead users to where they need to be.</span></span>

## <a name="problem-3-sometimes-ui-can-get-blocked-by-other-holograms"></a><span data-ttu-id="55771-131">问题 #3:有时 UI 可能会阻塞由其他全息</span><span class="sxs-lookup"><span data-stu-id="55771-131">Problem #3: Sometimes UI can get blocked by other holograms</span></span>

<span data-ttu-id="55771-132">有些的时候，当用户想要与一张全息图和其关联的用户界面控件进行交互，但它们会阻止视图，因为另一个全息图是在它们的前面。</span><span class="sxs-lookup"><span data-stu-id="55771-132">There are times when a user wants to interact with a hologram and its associated UI controls, but they are blocked from view because another hologram is in front of them.</span></span> <span data-ttu-id="55771-133">尽管我们已开发 HoloStudio，我们用于试验和错误发送给解决方案进行这。</span><span class="sxs-lookup"><span data-stu-id="55771-133">While we were developing HoloStudio, we used trial and error to come to a solution for this.</span></span>

![如果它与用户戴上 HoloLens 之间的另一个全息图，一张全息图与关联的 UI 控件可能被阻止。](images/ui-blocked-500px.jpg)

<span data-ttu-id="55771-135">我们尝试移动到用户的 UI 控件更接近，因此无法获取阻止，但找到它并不熟练的用户查看时同时查看远了一张全息图已接近您的控件。</span><span class="sxs-lookup"><span data-stu-id="55771-135">We tried moving the UI control closer to the user so it couldn't get blocked, but found that it wasn't comfortable for the user to look at a control that was near to you while simultaneously looking at a hologram that was far away.</span></span> <span data-ttu-id="55771-136">如果，但是，我们移动到用户控件最接近全息图的前面，他们认为像分离的全息图，应会影响从。</span><span class="sxs-lookup"><span data-stu-id="55771-136">If, however, we moved the control in front of the closest hologram to the user, they felt like it was detached from the hologram it should be affecting.</span></span>

<span data-ttu-id="55771-137">我们最后最终重像 UI 控件，并将其放相同距离时从用户作为全息图相关联，以便它们都认为已连接。</span><span class="sxs-lookup"><span data-stu-id="55771-137">We finally ended up ghosting the UI control, and put it at the same distance from the user as the hologram it's associated with, so they both feel connected.</span></span> <span data-ttu-id="55771-138">这允许用户与控件交互，即使已被遮盖。</span><span class="sxs-lookup"><span data-stu-id="55771-138">This allows the user to interact with the control even though it's been obscured.</span></span>

![解决方案： 我们幻像 UI 控件，同时允许与控件交互，并使其可以连接到的全息图，那么这影响。](images/ghosting-ui-500px.jpg)

<span data-ttu-id="55771-140">**我们了解到的内容**</span><span class="sxs-lookup"><span data-stu-id="55771-140">**What we learned**</span></span>

<span data-ttu-id="55771-141">用户需要能够轻松地访问 UI 控件，即使它们已被阻止，因此需弄清方法，以确保用户可以完成其任务，无论其全息现实世界中。</span><span class="sxs-lookup"><span data-stu-id="55771-141">Users need to be able to easily access UI controls even if they've been blocked, so figure out methods to ensure that users can complete their tasks no matter where their holograms are in the real world.</span></span>

## <a name="about-the-author"></a><span data-ttu-id="55771-142">关于作者</span><span class="sxs-lookup"><span data-stu-id="55771-142">About the author</span></span>

<table style="border-collapse:collapse">
<tr>
<td style="border-style: none" width="60"><img alt="Picture of Marcus Ghaly" width="60" height="60" src="images/marcus-ghaly-200px.jpg"></td>
<td style="border-style: none"><span data-ttu-id="55771-143"><b>Marcus Ghaly</b></span><span class="sxs-lookup"><span data-stu-id="55771-143"><b>Marcus Ghaly</b></span></span><br><span data-ttu-id="55771-144">部门高级 Holographic 设计器 @Microsoft</span><span class="sxs-lookup"><span data-stu-id="55771-144">Sr. Holographic Designer @Microsoft</span></span></td>
</tr>
</table>

## <a name="see-also"></a><span data-ttu-id="55771-145">请参阅</span><span class="sxs-lookup"><span data-stu-id="55771-145">See also</span></span>
* [<span data-ttu-id="55771-146">交互基础知识</span><span class="sxs-lookup"><span data-stu-id="55771-146">Interaction fundamentals</span></span>](interaction-fundamentals.md)

 