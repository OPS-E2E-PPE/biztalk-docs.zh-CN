---
title: 如何选择多个 Functoid |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 51f4528c-4846-4e02-9591-07e2fde131ae
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4cb72a036acaa39823c7cd2e4c3ab18ba4330dcc
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65334775"
---
# <a name="how-to-select-multiple-functoids"></a><span data-ttu-id="0c0e5-102">如何选择多个 Functoid</span><span class="sxs-lookup"><span data-stu-id="0c0e5-102">How to Select Multiple Functoids</span></span>
<span data-ttu-id="0c0e5-103">当处理大型映射，您可能想要在同一时间执行对多个 functoid 的操作。</span><span class="sxs-lookup"><span data-stu-id="0c0e5-103">When dealing with large maps, you may want to perform operations on multiple functoids at the same time.</span></span> <span data-ttu-id="0c0e5-104">在这种情况下，可以选择所有目标 functoid，然后执行操作。</span><span class="sxs-lookup"><span data-stu-id="0c0e5-104">In such cases, you can select all of the functoids of interest and then perform the operation.</span></span> <span data-ttu-id="0c0e5-105">这很有用，例如，如果想要连接的 functoid 及其连接的链接，以及一组移到另一个网格页。</span><span class="sxs-lookup"><span data-stu-id="0c0e5-105">This is useful, for example, when you want to move a set of connected functoids, and their connecting links, from one grid page to another.</span></span>  
  
### <a name="to-select-multiple-functoids-at-the-same-time"></a><span data-ttu-id="0c0e5-106">若要同时选择多个 functoid</span><span class="sxs-lookup"><span data-stu-id="0c0e5-106">To select multiple functoids at the same time</span></span>  
  
1.  <span data-ttu-id="0c0e5-107">在 BizTalk 映射器网格页上，单击第一个 functoid 以将其选中。</span><span class="sxs-lookup"><span data-stu-id="0c0e5-107">In BizTalk Mapper, in a grid page, click the first functoid to select it.</span></span> <span data-ttu-id="0c0e5-108">该 functoid 将突出显示。</span><span class="sxs-lookup"><span data-stu-id="0c0e5-108">The functoid is highlighted.</span></span>  
  
2.  <span data-ttu-id="0c0e5-109">在 BizTalk 映射器中，在相同的网格页中，按住 CTRL 或 SHIFT 键，然后单击另一个 functoid 将其同时选定。</span><span class="sxs-lookup"><span data-stu-id="0c0e5-109">In BizTalk Mapper, in the same grid page, hold down the CTRL or the SHIFT key, and then click another functoid to select it as well.</span></span> <span data-ttu-id="0c0e5-110">此 functoid 也会突出显示。</span><span class="sxs-lookup"><span data-stu-id="0c0e5-110">This functoid is highlighted too.</span></span>  
  
3.  <span data-ttu-id="0c0e5-111">重复步骤 2 所需选择所有目标 functoid。</span><span class="sxs-lookup"><span data-stu-id="0c0e5-111">Repeat step 2 as required to select all of the functoids of interest.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0c0e5-112">在网格页中的多项选择为 functoid 和链接同时工作，移动一系列连接的 functoid 和其连接到另一个链接从一个网格页时必须签名。</span><span class="sxs-lookup"><span data-stu-id="0c0e5-112">Multiple selection in a grid page work for functoids and links simultaneously, which is required when moving a set of connected functoids and their connecting links from one grid page to another.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c0e5-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="0c0e5-113">See Also</span></span>  
 <span data-ttu-id="0c0e5-114">[使用 Functoid 创建更复杂的映射](../core/using-functoids-to-create-more-complex-mappings.md) </span><span class="sxs-lookup"><span data-stu-id="0c0e5-114">[Using Functoids to Create More Complex Mappings](../core/using-functoids-to-create-more-complex-mappings.md) </span></span>  
 [<span data-ttu-id="0c0e5-115">如何选择多个链接和 Functoid</span><span class="sxs-lookup"><span data-stu-id="0c0e5-115">How to Select Multiple Links and Functoids</span></span>](../core/how-to-select-multiple-links-and-functoids.md)