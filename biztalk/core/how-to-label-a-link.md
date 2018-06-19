---
title: 如何标记链接 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5fb81763-8b50-4334-88a8-efad1c5d82d9
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c0e47a776fdbc8eccbc1037b3c73b069d810eee0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22253789"
---
# <a name="how-to-label-a-link"></a><span data-ttu-id="33ce9-102">如何标记链接</span><span class="sxs-lookup"><span data-stu-id="33ce9-102">How to Label a Link</span></span>
<span data-ttu-id="33ce9-103">标签有助于记录 functoid 的用途或映射中的链接。</span><span class="sxs-lookup"><span data-stu-id="33ce9-103">Labels are helpful to document the purpose of a functoid or a link in a map.</span></span> <span data-ttu-id="33ce9-104">你可以使用**标签**属性可以命名链接。</span><span class="sxs-lookup"><span data-stu-id="33ce9-104">You can use the **Label** property to name a link.</span></span> <span data-ttu-id="33ce9-105">当您的映射包含大型架构结构，并且标识到 functoid 的输入输出链接变得困难时，此功能很有用。</span><span class="sxs-lookup"><span data-stu-id="33ce9-105">This is useful when your map contains big schema structures and identifying the inputs and output links to a functoid becomes difficult.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="33ce9-106">有关如何标签和注释 functoid 的信息，请参阅[如何标记和注释 Functoid](../core/how-to-label-and-comment-a-functoid.md)。</span><span class="sxs-lookup"><span data-stu-id="33ce9-106">For information on how to label and comment functoids, see [How to Label and Comment a Functoid](../core/how-to-label-and-comment-a-functoid.md).</span></span>  
  
 <span data-ttu-id="33ce9-107">下图显示了一个链接标签。</span><span class="sxs-lookup"><span data-stu-id="33ce9-107">The following figure shows a link label.</span></span>  
  
 <span data-ttu-id="33ce9-108">![标签粘贴链接](../core/media/new-labelling-link.gif "New_Labelling_link")</span><span class="sxs-lookup"><span data-stu-id="33ce9-108">![Labelling a link](../core/media/new-labelling-link.gif "New_Labelling_link")</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="33ce9-109">先决条件</span><span class="sxs-lookup"><span data-stu-id="33ce9-109">Prerequisites</span></span>  
 <span data-ttu-id="33ce9-110">这些说明需要 BizTalk 映射器处于运行状态。</span><span class="sxs-lookup"><span data-stu-id="33ce9-110">These instructions require that BizTalk Mapper is running.</span></span>  
  
### <a name="to-add-a-label-to-a-link"></a><span data-ttu-id="33ce9-111">若要向链接添加标签</span><span class="sxs-lookup"><span data-stu-id="33ce9-111">To add a label to a link</span></span>  
  
1.  <span data-ttu-id="33ce9-112">选择要添加标签的链接。</span><span class="sxs-lookup"><span data-stu-id="33ce9-112">Select the link you want to label.</span></span>  
  
2.  <span data-ttu-id="33ce9-113">在**属性**窗口中，提供新名称出现在**标签**字段。</span><span class="sxs-lookup"><span data-stu-id="33ce9-113">In the **Properties** window, provide the new name in the **Label** field.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="33ce9-114">最大允许的字符数为 256。</span><span class="sxs-lookup"><span data-stu-id="33ce9-114">The maximum number of characters allowed is 256.</span></span> <span data-ttu-id="33ce9-115">如果指定超过 256 个字符的字符串，则接受前 256 个字符和其余部分将被丢弃。</span><span class="sxs-lookup"><span data-stu-id="33ce9-115">If a string with more than 256 characters is specified, the first 256 characters are accepted and the rest are discarded.</span></span>  
  
     <span data-ttu-id="33ce9-116">![链接标签属性](../core/media/new-to-label-link.gif "New_To_Label_Link")</span><span class="sxs-lookup"><span data-stu-id="33ce9-116">![Link label properties](../core/media/new-to-label-link.gif "New_To_Label_Link")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33ce9-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="33ce9-117">See Also</span></span>  
 [<span data-ttu-id="33ce9-118">使用链接以指定记录和字段映射</span><span class="sxs-lookup"><span data-stu-id="33ce9-118">Using Links to Specify Record and Field Mappings</span></span>](../core/using-links-to-specify-record-and-field-mappings.md)