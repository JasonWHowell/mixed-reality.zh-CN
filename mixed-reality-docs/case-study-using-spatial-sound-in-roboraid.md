---
title: 案例研究-在 RoboRaid 中使用空间的声音
description: 声音空间是 Microsoft HoloLens，提供用户认为这怎么回事针对这些对象时不可见的行的一种方法的最令人兴奋功能之一。
author: mattzmsft
ms.author: hakons
ms.date: 03/21/2018
ms.topic: article
keywords: Windows Mixed Reality HoloLens，RoboRaid，空间声音
ms.openlocfilehash: 4bb050b4a4051c121c488ea38e150a8973bd7c04
ms.sourcegitcommit: 384b0087899cd835a3a965f75c6f6c607c9edd1b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/12/2019
ms.locfileid: "59592125"
---
# <a name="case-study---using-spatial-sound-in-roboraid"></a><span data-ttu-id="eebc3-104">案例研究-在 RoboRaid 中使用空间的声音</span><span class="sxs-lookup"><span data-stu-id="eebc3-104">Case study - Using spatial sound in RoboRaid</span></span>

<span data-ttu-id="eebc3-105">Charles Sinex，音频 Microsoft HoloLens 体验团队主管，讨论了他创建的音频时遇到的独特挑战[RoboRaid](https://www.microsoft.com/en-us/p/roboraid/9nblggh5fv3j)，混合的现实第一人称射击。</span><span class="sxs-lookup"><span data-stu-id="eebc3-105">Charles Sinex, audio lead on the Microsoft HoloLens Experience Team, talks about the unique challenges he encountered when creating audio for [RoboRaid](https://www.microsoft.com/en-us/p/roboraid/9nblggh5fv3j), a mixed reality first-person shooter.</span></span>

## <a name="the-tech"></a><span data-ttu-id="eebc3-106">技术人员</span><span class="sxs-lookup"><span data-stu-id="eebc3-106">The tech</span></span>

<span data-ttu-id="eebc3-107">[空间声音](spatial-sound.md)是 Microsoft HoloLens，提供用户认为这怎么回事针对这些对象时不可见的行的一种方法的最令人兴奋的功能之一。</span><span class="sxs-lookup"><span data-stu-id="eebc3-107">[Spatial sound](spatial-sound.md) is one of the most exciting features of Microsoft HoloLens, providing a way for users to perceive what's going on around them when objects are out of the line of sight.</span></span>

<span data-ttu-id="eebc3-108">RoboRaid，最显而易见且最有效利用空间声音是播放机将外部用户的外围视觉发生警报。</span><span class="sxs-lookup"><span data-stu-id="eebc3-108">In RoboRaid, the most obvious and effective use of spatial sound is to alert the player to something happening outside of the user's peripheral vision.</span></span> <span data-ttu-id="eebc3-109">例如，Breacher 可以输入从任何扫描墙的协助，但如果不面向进入其中的位置，可能会错过。</span><span class="sxs-lookup"><span data-stu-id="eebc3-109">For example, the Breacher can enter from any of the scanned walls in the room, but if you're not facing the location where it's entering, you might miss it.</span></span> <span data-ttu-id="eebc3-110">提醒你此侵害，你将聆听来自其中输入 Breacher，从中可以了解需要迅速采取措施以将其停止的音频不同位。</span><span class="sxs-lookup"><span data-stu-id="eebc3-110">To alert you to this invasion, you'll hear a distinct bit of audio coming from where the Breacher is entering, which lets you know that you need to act quickly to stop it.</span></span>

## <a name="behind-the-scenes"></a><span data-ttu-id="eebc3-111">幕后</span><span class="sxs-lookup"><span data-stu-id="eebc3-111">Behind the scenes</span></span>

<span data-ttu-id="eebc3-112">创建空间声音 HoloLens 应用的过程是因此全新而独特，过去项目要用于引用缺乏可能会导致大量头划伤时遇到问题。</span><span class="sxs-lookup"><span data-stu-id="eebc3-112">The process of creating spatial sound for HoloLens apps is so new and unique and the lack of past projects to use for reference can lead to a lot of head scratching when you run into a problem.</span></span> <span data-ttu-id="eebc3-113">希望这些示例的音频挑战我们面对而使 RoboRaid 将帮助你在创建音频的你自己的应用。</span><span class="sxs-lookup"><span data-stu-id="eebc3-113">Hopefully, these examples of the audio challenges we faced while making RoboRaid will help you as you create audio for your own apps.</span></span>

### <a name="be-mindful-of-taxing-the-cpu"></a><span data-ttu-id="eebc3-114">请注意负担很重的 CPU</span><span class="sxs-lookup"><span data-stu-id="eebc3-114">Be mindful of taxing the CPU</span></span>

<span data-ttu-id="eebc3-115">可以在 CPU 上要求空间声音。</span><span class="sxs-lookup"><span data-stu-id="eebc3-115">Spatial sound can be demanding on the CPU.</span></span> <span data-ttu-id="eebc3-116">如 RoboRaid 忙体验是重要要保留的空间声音到下在任何给定时间的八个实例。</span><span class="sxs-lookup"><span data-stu-id="eebc3-116">For a busy experience like RoboRaid it was crucial to keep the instances of spatial sound to under eight at any given time.</span></span> <span data-ttu-id="eebc3-117">大多数情况下，很像设置不同的音频事件的实例的限制，以便达到此限制后执行此操作的任何实例将被中止一样简单。</span><span class="sxs-lookup"><span data-stu-id="eebc3-117">For the most part, it was as easy as setting the limit of instances of different audio events so that any instances that happen after the limit is reached are killed.</span></span> <span data-ttu-id="eebc3-118">例如，当无人机生成，其 screams 被限制为三个实例在任何给定时间。</span><span class="sxs-lookup"><span data-stu-id="eebc3-118">For example, when drones spawn, their screams are limited to three instances at any given time.</span></span> <span data-ttu-id="eebc3-119">假设可以同时生成只有大约四个无人机，三个 screams 的在很多，因为没有您的大脑可以跟踪的方法很多发音相似音频事件。</span><span class="sxs-lookup"><span data-stu-id="eebc3-119">Considering only about four drones can spawn at once, three screams are plenty since there’s no way your brain can keep track of that many similar-sounding audio events.</span></span> <span data-ttu-id="eebc3-120">这释放了资源，对于其他空间声音事件，例如敌人爆炸或投篮机会控制在正在准备的敌人。</span><span class="sxs-lookup"><span data-stu-id="eebc3-120">This freed up resources for other spatial sound events, like enemy explosions or enemies preparing to shoot.</span></span>

### <a name="rewarding-a-successful-dodge"></a><span data-ttu-id="eebc3-121">奖励成功避开</span><span class="sxs-lookup"><span data-stu-id="eebc3-121">Rewarding a successful dodge</span></span>

<span data-ttu-id="eebc3-122">Dodging 的机修工保养是游戏玩法 RoboRaid 中的最重要方面，而是，我们认为已真正独特的 HoloLens 体验之一。</span><span class="sxs-lookup"><span data-stu-id="eebc3-122">The dodging mechanic is one of the most important aspects of gameplay in RoboRaid, and also something that we felt was truly unique to the HoloLens experience.</span></span> <span data-ttu-id="eebc3-123">在这种情况下，我们想要让成功淡到播放机很有益处。</span><span class="sxs-lookup"><span data-stu-id="eebc3-123">As such, we wanted to make successful dodges very rewarding to the player.</span></span> <span data-ttu-id="eebc3-124">我们将 Doppler"whizz-通过"来听起来相当在早期开发过程中极具吸引力。</span><span class="sxs-lookup"><span data-stu-id="eebc3-124">We got the Doppler "whizz-by" to sound compelling fairly early on in the development.</span></span> <span data-ttu-id="eebc3-125">最初，我的计划是使用一个循环并对其进行操作中实时使用音量、 音调、 和筛选器。</span><span class="sxs-lookup"><span data-stu-id="eebc3-125">Initially, my plan was to use a loop and manipulate it in real-time using volume, pitch, and filter.</span></span> <span data-ttu-id="eebc3-126">此实现将非常复杂，因此提交资源真正开始生成这之前我们创建成本低廉的原型使用的资产的 Doppler 效果提供支持只是为了了解如何在其认为 \*。</span><span class="sxs-lookup"><span data-stu-id="eebc3-126">The implementation for this was going to be very elaborate, so before committing resources to actually build this we created a cheap prototype using an asset with the Doppler effect baked in just to find out how it felt\*.</span></span> <span data-ttu-id="eebc3-127">我们的人才开发了使此 whizz 的资产会播放完全 0.7 秒之前将播放机的 ear 过去 projectile 和结果感觉真了不起 ！</span><span class="sxs-lookup"><span data-stu-id="eebc3-127">Our talented dev made it so that this whizz-by asset would play back exactly 0.7 seconds before the projectile will have passed by the player’s ear and the results felt really amazing!</span></span> <span data-ttu-id="eebc3-128">不用说，我们借助更复杂的解决方案，并实现原型。</span><span class="sxs-lookup"><span data-stu-id="eebc3-128">Needless to say, we ditched the more complex solution and implemented the prototype.</span></span>

<span data-ttu-id="eebc3-129">\* \* (如果想要使用内置的 Doppler 效果创建音频资产详细信息，请查看 Charles Deenan 调用声音设计器项目[在 2 分钟 100 Whooshes](http://designingsound.org/2010/02/charles-deenen-special-100-whooshes-in-2-minutes/)。) \*</span><span class="sxs-lookup"><span data-stu-id="eebc3-129">\*\*(If you'd like more information about creating an audio asset with the Doppler effect built in, check out an article by sound designer Charles Deenan called [100 Whooshes in 2 Minutes](http://designingsound.org/2010/02/charles-deenen-special-100-whooshes-in-2-minutes/).) \*</span></span>
<br>
<span data-ttu-id="eebc3-130">![已成功逃避敌人的 projectile 奖励有令人满意 whizz 通过声音播放机。](images/successful-dodge-roboraid-500px.jpg)</span><span class="sxs-lookup"><span data-stu-id="eebc3-130">![Successfully dodging an enemy's projectile rewards the player with a satisfying whizz-by sound.](images/successful-dodge-roboraid-500px.jpg)</span></span>

### <a name="ditching-ineffective-sounds"></a><span data-ttu-id="eebc3-131">抛弃无效声音</span><span class="sxs-lookup"><span data-stu-id="eebc3-131">Ditching ineffective sounds</span></span>

<span data-ttu-id="eebc3-132">最初，我们有想要后它们成功减淡敌人 projectile，但我们决定抛弃这几个原因，爆炸式播放声音播放机后面。</span><span class="sxs-lookup"><span data-stu-id="eebc3-132">Originally, we had wanted to play an explosion sound behind the player once they’ve successfully dodged the enemy projectile, but we decided to ditch this for several reasons.</span></span> <span data-ttu-id="eebc3-133">首先，没有可以有效地 whizz 通过 SFX 我们用于避开。</span><span class="sxs-lookup"><span data-stu-id="eebc3-133">First, it didn’t feel as effective as the whizz-by SFX we used for the dodge.</span></span> <span data-ttu-id="eebc3-134">Projectile 碰到墙后端时，其他内容将发生的游戏，将很听起来太多掩码中。</span><span class="sxs-lookup"><span data-stu-id="eebc3-134">By the time the projectile hits a wall behind you, something else would have happened in the game that would pretty much mask that sound.</span></span> <span data-ttu-id="eebc3-135">其次，我们没有冲突在地板上，因此我们无法获取播放 projectile 命中而不是墙纸基底时的爆炸式增长。</span><span class="sxs-lookup"><span data-stu-id="eebc3-135">Secondly, we didn’t have collision on the floor, so we couldn’t get the explosion to play when the projectile hit the floor instead of the walls.</span></span> <span data-ttu-id="eebc3-136">并且，最后，没有空间声音的 CPU 开销。</span><span class="sxs-lookup"><span data-stu-id="eebc3-136">And finally, there was the CPU cost of spatial sound.</span></span> <span data-ttu-id="eebc3-137">Elite Scorpion 敌人 （一个可在墙上插座爬网） 具有投篮大约八个炮弹的特殊攻击。</span><span class="sxs-lookup"><span data-stu-id="eebc3-137">The Elite Scorpion enemy (one that can crawl inside the wall) has a special attack that shoots about eight projectiles.</span></span> <span data-ttu-id="eebc3-138">不仅未，使大量混乱的组合中，它还引入了 awful 噼啪因为它已达到 CPU 太难。</span><span class="sxs-lookup"><span data-stu-id="eebc3-138">Not only did that make a huge mess in the mix, it also introduced awful crackling because it was hitting the CPU too hard.</span></span>

### <a name="communicating-a-hit"></a><span data-ttu-id="eebc3-139">通信命中</span><span class="sxs-lookup"><span data-stu-id="eebc3-139">Communicating a hit</span></span>

<span data-ttu-id="eebc3-140">我们遇到一个有趣的问题号我们认为是唯一的 HoloLens 体验，这是有效地向播放机通信具有已命中的难度。</span><span class="sxs-lookup"><span data-stu-id="eebc3-140">An interesting issue we ran into, which we felt was unique to the HoloLens experience, was the difficulty of effectively communicating to the players that they have been hit.</span></span> <span data-ttu-id="eebc3-141">混合的现实体验的成功之处在于，故事发生的操作，您的感觉。</span><span class="sxs-lookup"><span data-stu-id="eebc3-141">What makes a mixed reality experience successful is the feeling that the story is happening to you.</span></span> <span data-ttu-id="eebc3-142">这意味着您必须要相信您会在您自己的客厅防范外星人机器人侵害。</span><span class="sxs-lookup"><span data-stu-id="eebc3-142">That means that you have to believe that YOU are fighting an alien robot invasion in your own living room.</span></span>

<span data-ttu-id="eebc3-143">播放机显然不会感觉就任何内容时它们会命中，因此我们需要找到一种方法真正服播放机坏了 happed 到它们的内容。</span><span class="sxs-lookup"><span data-stu-id="eebc3-143">Players obviously won't feel anything when they get hit, so we had to find a way to really convince the player that something bad had happed to them.</span></span> <span data-ttu-id="eebc3-144">在传统的游戏可能会看到可让您了解您的人物花费了一次点击，或屏幕可能会闪烁红色和您的人物的动画可能有点 grunt。</span><span class="sxs-lookup"><span data-stu-id="eebc3-144">In conventional games you might see an animation that lets you know your character has taken a hit, or the screen might flash red and your character might grunt a little.</span></span> <span data-ttu-id="eebc3-145">由于混合的现实体验中，这些类型的提示不起作用，我们决定视觉提示结合确实有些夸张的声音，表明你已经损坏。</span><span class="sxs-lookup"><span data-stu-id="eebc3-145">Since these types of cues don't work in a mixed reality experience, we decided to combine the visual cue with a really exaggerated sound that indicates you've taken damage.</span></span> <span data-ttu-id="eebc3-146">创建大声音，并使其因此突出其 ducked 下的所有内容的组合中。</span><span class="sxs-lookup"><span data-stu-id="eebc3-146">I created a big sound, and made it so prominent in the mix that it ducked everything down.</span></span> <span data-ttu-id="eebc3-147">然后，以使其突出显示更多，我们添加了短警告声音如同已接收的核 sub。</span><span class="sxs-lookup"><span data-stu-id="eebc3-147">Then, to make it stand out even more, we added a short warning sound as if a nuclear sub was sinking.</span></span> 
<br>
<span data-ttu-id="eebc3-148">![在播放机获取中 RoboRaid 冲击下，它们提供可视提示，请参阅，但还有一夸张则音频提示，告知他们他们已损坏。](images/player-hit-roboraid-500px.jpg)</span><span class="sxs-lookup"><span data-stu-id="eebc3-148">![When a player gets hit in RoboRaid, they see a visual cue, but also get an exaggerated audio cue that tells them they've taken damage.](images/player-hit-roboraid-500px.jpg)</span></span>

### <a name="getting-big-sound-from-small-speakers"></a><span data-ttu-id="eebc3-149">从小型扬声器获取大声音</span><span class="sxs-lookup"><span data-stu-id="eebc3-149">Getting big sound from small speakers</span></span>

<span data-ttu-id="eebc3-150">HoloLens 扬声器是设备的小型和浅色以满足需求，因此您不能期望听到过多低端。</span><span class="sxs-lookup"><span data-stu-id="eebc3-150">HoloLens speakers are small and light to suit the needs of the device, so you can’t expect to hear too much low-end.</span></span> <span data-ttu-id="eebc3-151">类似于面向智能手机或游戏手持设备、 声音的设计器和作曲家一定要注意其音频频率内容的开发。</span><span class="sxs-lookup"><span data-stu-id="eebc3-151">Similar to developing for smart phones or handheld gaming devices, sound designers and composers have to be mindful of the frequency content of their audio.</span></span> <span data-ttu-id="eebc3-152">我始终设计声音或写入完整的频率范围的音乐，因为戴耳机的用户的选项。</span><span class="sxs-lookup"><span data-stu-id="eebc3-152">I always design sounds or write music with full frequency range because wearing headphones is an option for the users.</span></span> <span data-ttu-id="eebc3-153">但是，若要确保与 HoloLens 发言人的兼容性，我运行测试偶尔通过 EQ 置于我刚好处理任何 DAW 的主机。</span><span class="sxs-lookup"><span data-stu-id="eebc3-153">However, to ensure compatibility with HoloLens speakers, I run a test occasionally by putting an EQ in the master of any DAW I happen to be working in.</span></span> <span data-ttu-id="eebc3-154">EQ 设置包括高反差筛选器大约 600 到 700 Hz （不太陡峭） 和低通筛选在大约 10 K （非常高）。</span><span class="sxs-lookup"><span data-stu-id="eebc3-154">The EQ setting consists of a high-pass filter around 600 to 700 Hz (not too steep) and low-pass filter at around 10K (very steep).</span></span> <span data-ttu-id="eebc3-155">应让您大致了解的如何将声音将在设备上的播放。</span><span class="sxs-lookup"><span data-stu-id="eebc3-155">That should give you a ballpark idea of how your sounds will playback on the device.</span></span>

<span data-ttu-id="eebc3-156">如果需要借助低音让更改音乐的同时按下的了解，可能会发现您的音乐完全失去根的意义上说，应用此 EQ 设置时。</span><span class="sxs-lookup"><span data-stu-id="eebc3-156">If you are relying on bass to give the sense of chord changing in your music, you may find that your music completely loses the sense of root when you apply this EQ setting.</span></span> <span data-ttu-id="eebc3-157">若要解决此问题，我添加另一层到的一个序号更高版本 （与某些丰富谐波） 是低音和混合它，以获得根后在意义。</span><span class="sxs-lookup"><span data-stu-id="eebc3-157">To remedy this, I added another layer to the bass that is one octave higher (with some rich harmonics) and mixed it to get the sense of root back.</span></span> <span data-ttu-id="eebc3-158">有时使用向上谐波人群失真将提供足够频率的内容在较高的范围，以使我们的大脑认为它下面的内容。</span><span class="sxs-lookup"><span data-stu-id="eebc3-158">Sometimes using distortion to amp up the harmonics will give enough frequency content in the upper range to make our brain think that there’s something underneath it.</span></span> <span data-ttu-id="eebc3-159">这适用于 SFX 影响、 爆炸或为特殊时刻的声音等如老板的超级攻击。</span><span class="sxs-lookup"><span data-stu-id="eebc3-159">This is true for SFX like impacts, explosions, or sounds for special moments, such as a boss' super attacks.</span></span> <span data-ttu-id="eebc3-160">确实不能依赖于低端让播放机的影响或权重的了解。</span><span class="sxs-lookup"><span data-stu-id="eebc3-160">You really can’t rely on the low-end to give the player a sense of impact or weight.</span></span> <span data-ttu-id="eebc3-161">与音乐，利用失真提供很少的危机一定帮助。</span><span class="sxs-lookup"><span data-stu-id="eebc3-161">As with music, using distortion to give a little bit of crunch definitely helped.</span></span>

### <a name="making-your-audio-cues-stand-out"></a><span data-ttu-id="eebc3-162">使您脱颖而出的音频提示</span><span class="sxs-lookup"><span data-stu-id="eebc3-162">Making your audio cues stand out</span></span>

<span data-ttu-id="eebc3-163">正常情况下，团队中的每个人都想 bombastic 音乐、 嘈杂枪支和疯狂爆炸;但它们还希望能够听到 voiceover 或任何其他游戏关键音频提示。</span><span class="sxs-lookup"><span data-stu-id="eebc3-163">Naturally, everyone on the team wanted bombastic music, loud guns, and crazy explosions; but they also wanted to be able to hear voiceover or any other game-critical audio cues.</span></span>

<span data-ttu-id="eebc3-164">在完整范围的频率的控制台游戏，可以有根据声音的重要程度划分频率的更多选项。</span><span class="sxs-lookup"><span data-stu-id="eebc3-164">On a console game with full range of frequency you have more options to divide frequencies up depending on the importance of the sound.</span></span> <span data-ttu-id="eebc3-165">但是，对于 RoboRaid，我已限制中的我无法从声音曲线的频率范围数。</span><span class="sxs-lookup"><span data-stu-id="eebc3-165">For RoboRaid, however, I was limited in the number of ranges of frequencies I could curve out from sounds.</span></span> <span data-ttu-id="eebc3-166">例如，如果您使用低通滤波器和掉过多内容从更高版本的范围末尾的曲线，无任何内容由于没有更低端中留下的声音。</span><span class="sxs-lookup"><span data-stu-id="eebc3-166">For instance, if you use low-pass filter and curve out too much from the higher end of the spectrum, you won’t have anything left on the sound because there’s not much low-end.</span></span>

<span data-ttu-id="eebc3-167">为了使 RoboRaid 声音可在设备上一样大，我们不得不较低的整体体验的动态范围，并广泛使用了放掉通过创建清晰的层次结构的不同类型的声音的重要性。</span><span class="sxs-lookup"><span data-stu-id="eebc3-167">In order to make RoboRaid sound as big as it can on the device, we had to lower the dynamic range of the whole experience and made extensive use of ducking by creating a clear hierarchy of importance for different types of sounds.</span></span> <span data-ttu-id="eebc3-168">我将设置从-2 放掉到-6 dB 根据重要程度。</span><span class="sxs-lookup"><span data-stu-id="eebc3-168">I set the ducking from -2 to -6 dB depending on the importance.</span></span> <span data-ttu-id="eebc3-169">我个人不喜欢明显放掉在游戏中，因此我花了很多优化淡入淡出输入/输出计时和卷衰减量的时间。</span><span class="sxs-lookup"><span data-stu-id="eebc3-169">I personally don’t like obvious ducking in games, so I spent a lot of time tuning the fade in/out timing and the amount of volume attenuation.</span></span> <span data-ttu-id="eebc3-170">我们设置单独总线空间声音、 非空间声音、 VO，和 dry 总线，而无需混响的音乐，则创建非常高的优先级，关键，和非关键总线。</span><span class="sxs-lookup"><span data-stu-id="eebc3-170">We set up separate busses for spatial sound, non-spatial sound, VO, and dry bus without reverb for music, then created very high priority, critical, and non-critical busses.</span></span> <span data-ttu-id="eebc3-171">资产已然后设置转到其相应的总线。</span><span class="sxs-lookup"><span data-stu-id="eebc3-171">The assets were then set up to go to their appropriate busses.</span></span>

<span data-ttu-id="eebc3-172">我希望有音频专业人员会尽可能多有趣和兴奋就像我一样正在致力于 RoboRaid 处理其自己的应用。</span><span class="sxs-lookup"><span data-stu-id="eebc3-172">I hope audio professionals out there will have as much fun and excitement working on their own apps as I did working on RoboRaid.</span></span> <span data-ttu-id="eebc3-173">我迫不及待地想看到 （和听到 ！） 什么 Microsoft 外部的天才人员会提供用于 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="eebc3-173">I can’t wait to see (and hear!) what the talented folks outside Microsoft will come up with for HoloLens.</span></span>

## <a name="do-it-yourself"></a><span data-ttu-id="eebc3-174">就自己动手</span><span class="sxs-lookup"><span data-stu-id="eebc3-174">Do it yourself</span></span>

<span data-ttu-id="eebc3-175">我发现，以使某些事件 （如爆炸） 听起来"较大的"的一个技巧-像它们填满空间 — 是创建空间声音的 mono 资产并将其与 2D 立体声资产，要播放以三维形式。</span><span class="sxs-lookup"><span data-stu-id="eebc3-175">One trick I discovered to make certain events (such as explosions) sound "bigger"—like they're filling up the room—was to create a mono asset for the spatial sound and mix it with a 2D stereo asset, to be played back in 3D.</span></span> <span data-ttu-id="eebc3-176">会占用一些优化，因为立体声内容中具有过多的信息将降低 mono 资产的方向性。</span><span class="sxs-lookup"><span data-stu-id="eebc3-176">It does take some tuning, since having too much information in the stereo content will lessen the directionality of the mono assets.</span></span> <span data-ttu-id="eebc3-177">但是，正确平衡会导致将让玩家着头看打开正确的方向的巨大声音。</span><span class="sxs-lookup"><span data-stu-id="eebc3-177">However, getting the balance right will result in huge sounds that will get players to turn their heads in the right direction.</span></span>

<span data-ttu-id="eebc3-178">你可以尝试自己使用下面的音频资产：</span><span class="sxs-lookup"><span data-stu-id="eebc3-178">You can try this yourself using the audio assets below:</span></span>

<span data-ttu-id="eebc3-179">**方案 1**</span><span class="sxs-lookup"><span data-stu-id="eebc3-179">**Scenario 1**</span></span>
1. <span data-ttu-id="eebc3-180">下载[roboraid_enemy_explo_mono.wav](images/roboraid-enemy-explo-mono.wav)和一组通过空间声音播放并将其分配给一个事件。</span><span class="sxs-lookup"><span data-stu-id="eebc3-180">Download [roboraid_enemy_explo_mono.wav](images/roboraid-enemy-explo-mono.wav) and set to playback through spatial sound and assign it to an event.</span></span>
2. <span data-ttu-id="eebc3-181">下载[roboraid_enemy_explo_stereo.wav](images/roboraid-enemy-explo-stereo.wav)和设置为在 2D 立体声设备中播放，并将分配给与上面相同的事件。</span><span class="sxs-lookup"><span data-stu-id="eebc3-181">Download [roboraid_enemy_explo_stereo.wav](images/roboraid-enemy-explo-stereo.wav) and set to playback in 2D stereo and assign to the same event as above.</span></span> <span data-ttu-id="eebc3-182">因为这些资产被规范化为 Unity 中，以便它不修剪衰减这两个资产的卷。</span><span class="sxs-lookup"><span data-stu-id="eebc3-182">Because these assets are normalized to Unity, attenuate volume of both assets so that it doesn’t clip.</span></span>
3. <span data-ttu-id="eebc3-183">一起玩这两种声音。</span><span class="sxs-lookup"><span data-stu-id="eebc3-183">Play both sounds together.</span></span> <span data-ttu-id="eebc3-184">将移动头脑大约感觉如何空间这听起来。</span><span class="sxs-lookup"><span data-stu-id="eebc3-184">Move your head around to feel how spatial it sounds.</span></span>

<span data-ttu-id="eebc3-185">**方案 2**</span><span class="sxs-lookup"><span data-stu-id="eebc3-185">**Scenario 2**</span></span>
1. <span data-ttu-id="eebc3-186">下载[roboraid_enemy_explo_summed.wav](images/roboraid-enemy-explo-summed.wav)和通过空间声音播放设置并将分配给一个事件。</span><span class="sxs-lookup"><span data-stu-id="eebc3-186">Download [roboraid_enemy_explo_summed.wav](images/roboraid-enemy-explo-summed.wav) and set to playback through spatial sound and assign to an event.</span></span>
2. <span data-ttu-id="eebc3-187">播放此资产本身，然后将其对事件进行比较从方案 1。</span><span class="sxs-lookup"><span data-stu-id="eebc3-187">Play this asset by itself then compare it to the event from Scenario 1.</span></span>
3. <span data-ttu-id="eebc3-188">请尝试不同的平衡 mono 和立体声文件。</span><span class="sxs-lookup"><span data-stu-id="eebc3-188">Try different balance of mono and stereo files.</span></span>

## <a name="about-the-author"></a><span data-ttu-id="eebc3-189">关于作者</span><span class="sxs-lookup"><span data-stu-id="eebc3-189">About the author</span></span>

<table style="border-collapse:collapse">
<tr>
<td style="border-style: none" width="60px"><img alt="Picture of Charles Sinex" width="60" height="60" src="images/genericusertile.jpg"></td>
<td style="border-style: none"><span data-ttu-id="eebc3-190"><b>Charles Sinex</b></span><span class="sxs-lookup"><span data-stu-id="eebc3-190"><b>Charles Sinex</b></span></span><br><span data-ttu-id="eebc3-191">音频工程师 @Microsoft</span><span class="sxs-lookup"><span data-stu-id="eebc3-191">Audio Engineer @Microsoft</span></span></td>
</tr>
</table>

## <a name="see-also"></a><span data-ttu-id="eebc3-192">请参阅</span><span class="sxs-lookup"><span data-stu-id="eebc3-192">See Also</span></span>
* [<span data-ttu-id="eebc3-193">空间声音</span><span class="sxs-lookup"><span data-stu-id="eebc3-193">Spatial sound</span></span>](spatial-sound.md)
* [<span data-ttu-id="eebc3-194">对于 Microsoft HoloLens RoboRaid</span><span class="sxs-lookup"><span data-stu-id="eebc3-194">RoboRaid for Microsoft HoloLens</span></span>](https://www.microsoft.com/en-us/p/roboraid/9nblggh5fv3j)