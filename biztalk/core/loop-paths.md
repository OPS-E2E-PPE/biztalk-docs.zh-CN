---
title: "循环路径 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Looping functoids, paths
- maps, conditional looping
ms.assetid: 4612dc2d-2c39-427d-88ac-65f9e85873c7
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e69e7d1c092ee5ca34b8c2ef3f309eff6c44b271
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="loop-paths"></a><span data-ttu-id="7888d-102">循环路径</span><span class="sxs-lookup"><span data-stu-id="7888d-102">Loop Paths</span></span>
<span data-ttu-id="7888d-103">如果其最大出现次数属性大于 1 就循环架构中的元素。</span><span class="sxs-lookup"><span data-stu-id="7888d-103">An element in a schema is looping if its Max Occurs property is greater than 1.</span></span> <span data-ttu-id="7888d-104">源架构中的循环元素和目标架构中的循环元素之间绘制的链接时发生循环路径。</span><span class="sxs-lookup"><span data-stu-id="7888d-104">A loop path occurs when you draw a link between a looping element in the source schema and a looping element in the destination schema.</span></span>  
  
## <a name="configuring-a-loop-path"></a><span data-ttu-id="7888d-105">配置循环路径</span><span class="sxs-lookup"><span data-stu-id="7888d-105">Configuring a Loop Path</span></span>  
 <span data-ttu-id="7888d-106">创建循环路径时，BizTalk 映射程序自动处理循环记录。</span><span class="sxs-lookup"><span data-stu-id="7888d-106">BizTalk Mapper automatically handles the looping records when you create a loop path.</span></span>  
  
 <span data-ttu-id="7888d-107">通过将源架构的循环记录中的字段链接到目标架构的循环记录中的字段，可以在映射中配置循环路径。</span><span class="sxs-lookup"><span data-stu-id="7888d-107">You can configure a loop path in a map by linking a field in a looping record in the source schema to a field that is in a looping record in the destination schema.</span></span> <span data-ttu-id="7888d-108">下图显示的是仅将食品调查记录复制到主地址列表的映射。</span><span class="sxs-lookup"><span data-stu-id="7888d-108">The figure below shows a map that copies only food survey records into a master address list.</span></span>  
  
 <span data-ttu-id="7888d-109">![映射用法循环路径。] (../core/media/correct-loop-path-map.gif "correct_loop_path_map")</span><span class="sxs-lookup"><span data-stu-id="7888d-109">![Map illustrating the use of a loop path.](../core/media/correct-loop-path-map.gif "correct_loop_path_map")</span></span>  
<span data-ttu-id="7888d-110">循环路径映射</span><span class="sxs-lookup"><span data-stu-id="7888d-110">Loop Path Map</span></span>  
  
## <a name="multiple-loop-paths"></a><span data-ttu-id="7888d-111">多个循环路径</span><span class="sxs-lookup"><span data-stu-id="7888d-111">Multiple Loop Paths</span></span>  
 <span data-ttu-id="7888d-112">如果将包含于两个或多个循环记录中的字段链接到包含于单个循环记录中的字段，则会形成多个循环路径。</span><span class="sxs-lookup"><span data-stu-id="7888d-112">A multiple loop path occurs in a map when you link fields contained by two or more looping records to fields contained in a single looping record.</span></span> <span data-ttu-id="7888d-113">下图显示的是尝试将两个不同调查中收集的地址合并为单个主地址列表。</span><span class="sxs-lookup"><span data-stu-id="7888d-113">The following figure shows an attempt to combine addresses collected from two different surveys into a single master address list.</span></span>  
  
 <span data-ttu-id="7888d-114">![具有多个循环路径映射](../core/media/multiple-loop-path-map.gif "multiple_loop_path_map")</span><span class="sxs-lookup"><span data-stu-id="7888d-114">![Map with multiple loop paths](../core/media/multiple-loop-path-map.gif "multiple_loop_path_map")</span></span>  
<span data-ttu-id="7888d-115">具有多个循环路径的映射（不正确）</span><span class="sxs-lookup"><span data-stu-id="7888d-115">Map With Multiple Loop Paths (Incorrect)</span></span>  
  
 <span data-ttu-id="7888d-116">此映射将不会产生预期的结果。</span><span class="sxs-lookup"><span data-stu-id="7888d-116">This map will not produce the expected results.</span></span> <span data-ttu-id="7888d-117">当映射器在编译过程中遇到多个循环路径时，它将生成一条警告，并默认选择第一个循环路径。</span><span class="sxs-lookup"><span data-stu-id="7888d-117">When the Mapper encounters multiple loop paths during compilation, it produces a warning and selects the first loop path by default.</span></span> <span data-ttu-id="7888d-118">若要将两个不同地址组合到单个主地址列表中，使用**循环**functoid 以下地图中所示。</span><span class="sxs-lookup"><span data-stu-id="7888d-118">In order to combine the two different addresses into a single master address list, use a **Looping** functoid as shown in the map below.</span></span>  
  
 <span data-ttu-id="7888d-119">![映射的循环 functoid 用法。] (../core/media/loopingfunctoid.gif "loopingfunctoid")</span><span class="sxs-lookup"><span data-stu-id="7888d-119">![Map illustrating the use of the looping functoid.](../core/media/loopingfunctoid.gif "loopingfunctoid")</span></span>  
<span data-ttu-id="7888d-120">“循环”Functoid 映射（正确）</span><span class="sxs-lookup"><span data-stu-id="7888d-120">Looping Functoid Map (Correct)</span></span>  
  
 <span data-ttu-id="7888d-121">**循环**functoid 应使用而不是在以下情况中的多个循环路径：</span><span class="sxs-lookup"><span data-stu-id="7888d-121">The **Looping** functoid should be used instead of multiple loop paths in the following scenarios:</span></span>  
  
1.  <span data-ttu-id="7888d-122">当映射器在多个循环路径方案中未产生所期望的输出结果时。</span><span class="sxs-lookup"><span data-stu-id="7888d-122">When the Mapper does not produce the desired output in a multiple loop paths scenario.</span></span>  
  
2.  <span data-ttu-id="7888d-123">要将输入实例消息中的多个重复结构合并为输出实例消息中的单个重复结构。</span><span class="sxs-lookup"><span data-stu-id="7888d-123">To combine multiple repeating structures in an input instance message into a single repeating structure in the output instance message.</span></span>  
  
3.  <span data-ttu-id="7888d-124">要通过将单个记录映射到多个记录将平面架构转换为分层架构。</span><span class="sxs-lookup"><span data-stu-id="7888d-124">To convert a flat schema to a hierarchical schema by mapping a single record to multiple records.</span></span> <span data-ttu-id="7888d-125">将平面架构转换为 Microsoft Commerce Server 目录时通常会执行此操作。</span><span class="sxs-lookup"><span data-stu-id="7888d-125">This is a common operation in converting flat schemas to Microsoft Commerce Server catalogs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7888d-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7888d-126">See Also</span></span>  
 <span data-ttu-id="7888d-127">[如何添加循环到图 Functoid](../core/how-to-add-looping-functoids-to-a-map.md) </span><span class="sxs-lookup"><span data-stu-id="7888d-127">[How to Add Looping Functoids to a Map](../core/how-to-add-looping-functoids-to-a-map.md) </span></span>  
 [<span data-ttu-id="7888d-128">循环 Functoid</span><span class="sxs-lookup"><span data-stu-id="7888d-128">Looping Functoid</span></span>](../core/looping-functoid.md)