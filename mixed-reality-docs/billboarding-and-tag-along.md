---
title: 公告板和尾随
description: 公告板的对象始终定位自身面临着用户。
author: radicalad
ms.author: adlinv
ms.date: 03/21/2018
ms.topic: article
keywords: Windows Mixed Reality，公告板，尾随
ms.openlocfilehash: 8215b96aff1f3c2d43e959f04ad83d41ffd32b2a
ms.sourcegitcommit: 384b0087899cd835a3a965f75c6f6c607c9edd1b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/12/2019
ms.locfileid: "59592629"
---
# <a name="billboarding-and-tag-along"></a><span data-ttu-id="57c6c-104">公告板和尾随</span><span class="sxs-lookup"><span data-stu-id="57c6c-104">Billboarding and tag-along</span></span>

<span data-ttu-id="57c6c-105">公告板是混合现实中应用于对象的行为概念。</span><span class="sxs-lookup"><span data-stu-id="57c6c-105">Billboarding is a behavioral concept that can be applied to objects in mixed reality.</span></span> <span data-ttu-id="57c6c-106">公告板的对象始终定位自身面临着用户。</span><span class="sxs-lookup"><span data-stu-id="57c6c-106">Objects with billboarding always orient themselves to face the user.</span></span> <span data-ttu-id="57c6c-107">这会非常有用的文本和静态对象 （世界锁定） 的用户的环境中的放置位置的面前系统会模糊或不可读，如果用户四处移动。</span><span class="sxs-lookup"><span data-stu-id="57c6c-107">This is especially helpful with text and menuing systems where static objects placed in the user's environment (world-locked) would be otherwise obscured or unreadable if a user were to move around.</span></span>

<span data-ttu-id="57c6c-108">![HoloLens 的菜单系统的角度来看，始终面临用户](images/billboarding-fragments.gif)</span><span class="sxs-lookup"><span data-stu-id="57c6c-108">![HoloLens perspective of a menu system that always faces the user](images/billboarding-fragments.gif)</span></span><br>
<span data-ttu-id="57c6c-109">*HoloLens 的菜单系统的角度来看，始终面临用户*</span><span class="sxs-lookup"><span data-stu-id="57c6c-109">*HoloLens perspective of a menu system that always faces the user*</span></span>

<span data-ttu-id="57c6c-110">公告板启用的对象可以自由地旋转中的用户环境。</span><span class="sxs-lookup"><span data-stu-id="57c6c-110">Objects with billboarding enabled can rotate freely in the user's environment.</span></span> <span data-ttu-id="57c6c-111">它们还可以限制于单个轴具体取决于设计注意事项。</span><span class="sxs-lookup"><span data-stu-id="57c6c-111">They can also be constrained to a single axis depending on design considerations.</span></span> <span data-ttu-id="57c6c-112">请记住，billboarded 的对象可能剪辑或遮蔽本身，如果放置太靠近其他对象，或在 HoloLens，太靠近扫描图面。</span><span class="sxs-lookup"><span data-stu-id="57c6c-112">Keep in mind, billboarded objects may clip or occlude themselves if they are placed too close to other objects, or in HoloLens, too close scanned surfaces.</span></span> <span data-ttu-id="57c6c-113">若要避免此问题，应考虑的总占用量为公告板启用轴上旋转时，可能会产生一个对象。</span><span class="sxs-lookup"><span data-stu-id="57c6c-113">To avoid this, think about the total footprint an object may produce when rotated on the axis enabled for billboarding.</span></span>

## <a name="what-is-a-tag-along"></a><span data-ttu-id="57c6c-114">什么是尾随？</span><span class="sxs-lookup"><span data-stu-id="57c6c-114">What is a tag-along?</span></span>

<span data-ttu-id="57c6c-115">尾随是可以添加到全息，包括 billboarded 的对象的行为概念。</span><span class="sxs-lookup"><span data-stu-id="57c6c-115">Tag-along is a behavioral concept that can be added to holograms, including billboarded objects.</span></span> <span data-ttu-id="57c6c-116">这种交互是实现头锁定内容的效果的更自然且友好的方式。</span><span class="sxs-lookup"><span data-stu-id="57c6c-116">This interaction is a more natural and friendly way of achieving the effect of head-locked content.</span></span> <span data-ttu-id="57c6c-117">尾随对象尝试从不离开用户的视图。</span><span class="sxs-lookup"><span data-stu-id="57c6c-117">A tag-along object attempts to never leave the user's view.</span></span> <span data-ttu-id="57c6c-118">这样，用户可以自由地与前面的它们时仍然会看到其直接视图之外全息进行交互。</span><span class="sxs-lookup"><span data-stu-id="57c6c-118">This allows the user to freely interact with what is front of them while also still seeing the holograms outside their direct view.</span></span>

<span data-ttu-id="57c6c-119">![HoloLens pin 面板是尾随的行为方式的一个极好示例](images/tagalong-1000px.jpg)</span><span class="sxs-lookup"><span data-stu-id="57c6c-119">![The HoloLens pins panel is a great example of how tag-along behaves](images/tagalong-1000px.jpg)</span></span><br>
<span data-ttu-id="57c6c-120">*HoloLens 开始菜单是尾随行为的一个极好示例*</span><span class="sxs-lookup"><span data-stu-id="57c6c-120">*The HoloLens Start menu is a great example of tag-along behavior*</span></span>

<span data-ttu-id="57c6c-121">尾随对象具有可以精细调整他们的行为的方式的参数。</span><span class="sxs-lookup"><span data-stu-id="57c6c-121">Tag-along objects have parameters which can fine-tune the way they behave.</span></span> <span data-ttu-id="57c6c-122">内容可以是入或移出用户的直通根据需要，围绕其环境中的移动用户。</span><span class="sxs-lookup"><span data-stu-id="57c6c-122">Content can be in or out of the user’s line of sight as desired while the user moves around their environment.</span></span> <span data-ttu-id="57c6c-123">当用户移动时，内容将尝试通过指向视图的边缘滑动人员在用户的外围中，具体取决于用户的移动速度可能会使对临时视图之外的内容。</span><span class="sxs-lookup"><span data-stu-id="57c6c-123">As the user moves, the content will attempt to stay within the user’s periphery by sliding towards the edge of the view, depending on how quickly a user moves may leave the content temporarily out of view.</span></span> <span data-ttu-id="57c6c-124">时用户 gazes 针对尾随对象，它更充分发挥视图。</span><span class="sxs-lookup"><span data-stu-id="57c6c-124">When the user gazes towards the tag-along object, it comes more fully into view.</span></span> <span data-ttu-id="57c6c-125">将始终被"快速消失"，以便用户永远不会忘记其内容是在哪个方向的内容。</span><span class="sxs-lookup"><span data-stu-id="57c6c-125">Think of content always being "a glance away" so users never forget what direction their content is in.</span></span>

<span data-ttu-id="57c6c-126">其他参数可以使感觉附加到用户的头通过使用橡胶带尾随对象。</span><span class="sxs-lookup"><span data-stu-id="57c6c-126">Additional parameters can make the tag-along object feel attached to the user's head by a rubber band.</span></span> <span data-ttu-id="57c6c-127">抑制加速或减速效果赋予对象使其感觉更实际存在的权重。</span><span class="sxs-lookup"><span data-stu-id="57c6c-127">Dampening acceleration or deceleration gives weight to the object making it feel more physically present.</span></span> <span data-ttu-id="57c6c-128">此 spring 行为是可帮助用户生成尾随的工作原理的准确心理模型功能可见性:。</span><span class="sxs-lookup"><span data-stu-id="57c6c-128">This spring behavior is an affordance that helps the user build an accurate mental model of how tag-along works.</span></span> <span data-ttu-id="57c6c-129">音频可帮助用户在尾随模式下具有对象时提供的其他提示。</span><span class="sxs-lookup"><span data-stu-id="57c6c-129">Audio helps provide additional affordances for when users have objects in tag-along mode.</span></span> <span data-ttu-id="57c6c-130">音频应强调的速度移动;一个快速头轮次应提供更明显的声音效果，而根本速度自然的每个步骤应该会有最小的音频，如果有影响。</span><span class="sxs-lookup"><span data-stu-id="57c6c-130">Audio should reinforce the speed of movement; a fast head turn should provide a more noticeable sound effect while walking at a natural speed should have minimal audio if any effects at all.</span></span>

<span data-ttu-id="57c6c-131">就像真正头锁定内容尾随对象具有非常庞大的或 nauseating 如果他们大幅变化移动或 spring 太多的用户视图中。</span><span class="sxs-lookup"><span data-stu-id="57c6c-131">Just like truly head-locked content, tag-along objects can prove overwhelming or nauseating if they move wildly or spring too much in the user’s view.</span></span> <span data-ttu-id="57c6c-132">为用户查找，然后快速停止，其方式告诉他们已停止。</span><span class="sxs-lookup"><span data-stu-id="57c6c-132">As a user looks around and then quickly stop, their senses tell them they have stopped.</span></span> <span data-ttu-id="57c6c-133">其平衡告知他们，其头已停止启用以及其视觉看到打开世界上停止。</span><span class="sxs-lookup"><span data-stu-id="57c6c-133">Their balance informs them that their head has stopped turning as well as their vision sees the world stop turning.</span></span> <span data-ttu-id="57c6c-134">但是，如果用户已停止时，尾随上继续移动，它可能将其理解混淆。</span><span class="sxs-lookup"><span data-stu-id="57c6c-134">However, if tag-along keeps on moving when the user has stopped, it may confuse their senses.</span></span>

## <a name="see-also"></a><span data-ttu-id="57c6c-135">请参阅</span><span class="sxs-lookup"><span data-stu-id="57c6c-135">See also</span></span>
* [<span data-ttu-id="57c6c-136">游标</span><span class="sxs-lookup"><span data-stu-id="57c6c-136">Cursors</span></span>](cursors.md)
* [<span data-ttu-id="57c6c-137">交互基础知识</span><span class="sxs-lookup"><span data-stu-id="57c6c-137">Interaction fundamentals</span></span>](interaction-fundamentals.md)
* [<span data-ttu-id="57c6c-138">Comfort</span><span class="sxs-lookup"><span data-stu-id="57c6c-138">Comfort</span></span>](comfort.md)