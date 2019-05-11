---
title: 如何强调映射项 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a2732b36-ca57-4566-ba26-da27a3082f32
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5be500ad36b27848733863ffde1a648d42c7db17
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385150"
---
# <a name="how-to-emphasize-map-items"></a><span data-ttu-id="152a6-102">如何强调映射项</span><span class="sxs-lookup"><span data-stu-id="152a6-102">How to Emphasize Map Items</span></span>
<span data-ttu-id="152a6-103">在 BizTalk 映射器中，在选择地图项中，所有相关的链接和 functoid 的强调程度。</span><span class="sxs-lookup"><span data-stu-id="152a6-103">In the BizTalk Mapper, when you select a map item, all the associated links and functoids are emphasized.</span></span> <span data-ttu-id="152a6-104">这可在映射中许多链接，其中很难识别关系和相关的架构项。</span><span class="sxs-lookup"><span data-stu-id="152a6-104">This is useful in maps with many links, where it is difficult to identify a relationship and the related schema items.</span></span>  
  
 <span data-ttu-id="152a6-105">当选择链接、 functoid 或架构元素时，BizTalk 映射器强调相关的关系和架构元素。</span><span class="sxs-lookup"><span data-stu-id="152a6-105">When you select a link, a functoid, or a schema element, the BizTalk Mapper emphasizes the related relationship and schema elements.</span></span> <span data-ttu-id="152a6-106">对于选定的映射项中，所有中突出显示的传入链接和传出链接 （递归） 粗体和所有其他映射项目将灰显。下面的屏幕截图显示选定的映射项以粗体显示，并显示较浅的颜色和其他映射项目。</span><span class="sxs-lookup"><span data-stu-id="152a6-106">For the selected map item, all the incoming links and the outgoing links (recursively) are highlighted in bold, and all the other map items are greyed out. The following screenshot shows the selected map item in bold and color and the other map items appear lighter.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="152a6-107">在此上下文中，相关的关系意思是直接或间接地链接到选定的映射项的所有链接、 functoid 或架构元素。</span><span class="sxs-lookup"><span data-stu-id="152a6-107">In this context, a related relationship means all the links, functoids, or schema elements directly or indirectly linked to the selected map item.</span></span>  
  
 <span data-ttu-id="152a6-108">![强调映射项](../core/media/mapper-intelliselect.gif "Mapper_IntelliSelect")</span><span class="sxs-lookup"><span data-stu-id="152a6-108">![Emphasizing a map item](../core/media/mapper-intelliselect.gif "Mapper_IntelliSelect")</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="152a6-109">先决条件</span><span class="sxs-lookup"><span data-stu-id="152a6-109">Prerequisites</span></span>  
 <span data-ttu-id="152a6-110">此操作需要 BizTalk 映射器正在运行。</span><span class="sxs-lookup"><span data-stu-id="152a6-110">This operation requires that BizTalk Mapper is running.</span></span>  
  
## <a name="to-emphasize-a-map-item"></a><span data-ttu-id="152a6-111">若要强调映射项</span><span class="sxs-lookup"><span data-stu-id="152a6-111">To emphasize a map item</span></span>  
  
-   <span data-ttu-id="152a6-112">单击一个映射项 （链接、 functoid 或架构元素）。</span><span class="sxs-lookup"><span data-stu-id="152a6-112">Click a map item (a link, a functoid, or a schema element).</span></span> <span data-ttu-id="152a6-113">您可以看到突出显示所有其他链接和 functoid （包括架构节点） 与当前网格页中选定的映射项相关联。</span><span class="sxs-lookup"><span data-stu-id="152a6-113">You can see that all the other links and functoids (including the schema nodes) associated with the selected map item in the current grid page are highlighted.</span></span>  
  
     <span data-ttu-id="152a6-114">有时，对于所选节点，可能有其他网格页中存在的关系。</span><span class="sxs-lookup"><span data-stu-id="152a6-114">Sometimes, for the selected node, there might be relationships existing in other grid pages.</span></span> <span data-ttu-id="152a6-115">在这种情况下，BizTalk 映射器强调当前网格页中的实例，并还会突出显示与所选节点的其他相关的关系所在的页选项卡。</span><span class="sxs-lookup"><span data-stu-id="152a6-115">In such a case, the BizTalk Mapper emphasizes the instance in current grid page and also highlights the page tab where the other related relationship to the selected node exists.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="152a6-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="152a6-116">See Also</span></span>  
 [<span data-ttu-id="152a6-117">使用 BizTalk 映射器中的增强功能</span><span class="sxs-lookup"><span data-stu-id="152a6-117">Using Enhanced Features in BizTalk Mapper</span></span>](../core/using-enhanced-features-in-biztalk-mapper.md)