---
title: "如何解决映射警告和错误 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e8a3e7f3-c96c-4d3d-9f7c-d2bfd9ace4fd
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1a2983a53bb47aa66d1564772d0f8e033132e5a8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-resolve-map-warnings-and-errors"></a><span data-ttu-id="4a3bd-102">如何解决映射警告和错误</span><span class="sxs-lookup"><span data-stu-id="4a3bd-102">How to Resolve Map Warnings and Errors</span></span>
<span data-ttu-id="4a3bd-103">在编译映射时，可能会在编译过程中显示警告和错误。</span><span class="sxs-lookup"><span data-stu-id="4a3bd-103">When you compile a map, you may find that warnings and errors result from the compilation process.</span></span>  
  
## <a name="resolve-warnings-and-errors-when-building-a-map"></a><span data-ttu-id="4a3bd-104">解决警告和错误时生成映射</span><span class="sxs-lookup"><span data-stu-id="4a3bd-104">Resolve warnings and errors when building a map</span></span>  
  
1.  <span data-ttu-id="4a3bd-105">对于链接和 functoid 错误，在**错误列表**窗口中，双击任何说明。</span><span class="sxs-lookup"><span data-stu-id="4a3bd-105">For link and functoid errors, in the **Error List** window, double-click any description.</span></span>  
  
     <span data-ttu-id="4a3bd-106">此时将突出显示与该错误相关的链接、functoid 或架构节点。</span><span class="sxs-lookup"><span data-stu-id="4a3bd-106">The link, functoid, or the schema node associated with the error is highlighted.</span></span> <span data-ttu-id="4a3bd-107">解决该问题。</span><span class="sxs-lookup"><span data-stu-id="4a3bd-107">Resolve the issue.</span></span>  
  
2.  <span data-ttu-id="4a3bd-108">查看**说明**中的区域**错误列表**窗口来确定其他错误。</span><span class="sxs-lookup"><span data-stu-id="4a3bd-108">Review the **Description** area in the **Error List** window to determine additional errors.</span></span>  
  
3.  <span data-ttu-id="4a3bd-109">单击**输出**窗口选项卡以查看其他警告和错误消息信息。</span><span class="sxs-lookup"><span data-stu-id="4a3bd-109">Click the **Output** window tab to view additional warning and error message information.</span></span>  
  
4.  <span data-ttu-id="4a3bd-110">解决了所有问题后，右键单击解决方案资源管理器中的映射文件名称，然后单击**测试映射**或**生成解决方案**、，具体情况而定。</span><span class="sxs-lookup"><span data-stu-id="4a3bd-110">After you have resolved all issues, right-click the map file name in Solution Explorer, and then click **Test Map** or **Build Solution**, as the case may be.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="4a3bd-111">如果显示警告，则可能在多个网格页中都存在该问题。</span><span class="sxs-lookup"><span data-stu-id="4a3bd-111">If a warning appears, the problem might exist over several grid pages.</span></span> <span data-ttu-id="4a3bd-112">例如，你有一条记录的网格页 1 (名为**项**) 在源架构树链接到一条记录 (名为**数**) 目标架构树中。</span><span class="sxs-lookup"><span data-stu-id="4a3bd-112">For example, you have grid page 1 with a record (named **Item**) in the source schema tree linked to a record (named **Number**) in the destination schema tree.</span></span> <span data-ttu-id="4a3bd-113">在网格的第 2 页中，你将有一个记录 (名为**产品**) 在源架构树链接到相同**数**目标架构树中的记录。</span><span class="sxs-lookup"><span data-stu-id="4a3bd-113">On grid page 2 you have a record (named **Product**) in the source schema tree linked to the same **Number** record in the destination schema tree.</span></span> <span data-ttu-id="4a3bd-114">在此方案中，将生成警告消息，指出你具有对同一记录的多个输入。</span><span class="sxs-lookup"><span data-stu-id="4a3bd-114">In this scenario, a warning message is generated stating that you have multiple inputs to the same record.</span></span> <span data-ttu-id="4a3bd-115">但是如果您查看网格的第 1 页，你看到只有一个输入**数**记录。</span><span class="sxs-lookup"><span data-stu-id="4a3bd-115">However if you view grid page 1, you see only one input into the **Number** record.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="4a3bd-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4a3bd-116">See Also</span></span>  
 <span data-ttu-id="4a3bd-117">[编译和测试映射](../core/compiling-and-testing-maps.md) </span><span class="sxs-lookup"><span data-stu-id="4a3bd-117">[Compiling and Testing Maps](../core/compiling-and-testing-maps.md) </span></span>  
 <span data-ttu-id="4a3bd-118">[BizTalk 映射程序错误](../core/biztalk-mapper-errors.md) </span><span class="sxs-lookup"><span data-stu-id="4a3bd-118">[BizTalk Mapper Errors](../core/biztalk-mapper-errors.md) </span></span>  
 [<span data-ttu-id="4a3bd-119">排除地图故障</span><span class="sxs-lookup"><span data-stu-id="4a3bd-119">Troubleshooting Maps</span></span>](../core/troubleshooting-maps.md)