---
title: 如何标记链接 |Microsoft Docs
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
ms.openlocfilehash: ba6bbe74c77cba09ba5098810d8782cde592e55f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65336940"
---
# <a name="how-to-label-a-link"></a><span data-ttu-id="8cac7-102">如何标记链接</span><span class="sxs-lookup"><span data-stu-id="8cac7-102">How to Label a Link</span></span>
<span data-ttu-id="8cac7-103">标签是有助于记录 functoid 或映射中的链接的用途。</span><span class="sxs-lookup"><span data-stu-id="8cac7-103">Labels are helpful to document the purpose of a functoid or a link in a map.</span></span> <span data-ttu-id="8cac7-104">可以使用**标签**属性对链接进行命名。</span><span class="sxs-lookup"><span data-stu-id="8cac7-104">You can use the **Label** property to name a link.</span></span> <span data-ttu-id="8cac7-105">您的映射包含大型架构结构和标识的输入和指向 functoid 的输出链接变得困难时，这很有用。</span><span class="sxs-lookup"><span data-stu-id="8cac7-105">This is useful when your map contains big schema structures and identifying the inputs and output links to a functoid becomes difficult.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8cac7-106">有关如何标记和注释 functoid 的信息，请参阅[如何标签和注释 Functoid](../core/how-to-label-and-comment-a-functoid.md)。</span><span class="sxs-lookup"><span data-stu-id="8cac7-106">For information on how to label and comment functoids, see [How to Label and Comment a Functoid](../core/how-to-label-and-comment-a-functoid.md).</span></span>  
  
 <span data-ttu-id="8cac7-107">下图显示链接标签。</span><span class="sxs-lookup"><span data-stu-id="8cac7-107">The following figure shows a link label.</span></span>  
  
 <span data-ttu-id="8cac7-108">![为链接添加标签](../core/media/new-labelling-link.gif "New_Labelling_link")</span><span class="sxs-lookup"><span data-stu-id="8cac7-108">![Labelling a link](../core/media/new-labelling-link.gif "New_Labelling_link")</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="8cac7-109">先决条件</span><span class="sxs-lookup"><span data-stu-id="8cac7-109">Prerequisites</span></span>  
 <span data-ttu-id="8cac7-110">这些说明需要 BizTalk 映射器处于运行状态。</span><span class="sxs-lookup"><span data-stu-id="8cac7-110">These instructions require that BizTalk Mapper is running.</span></span>  
  
### <a name="to-add-a-label-to-a-link"></a><span data-ttu-id="8cac7-111">若要向链接添加标签</span><span class="sxs-lookup"><span data-stu-id="8cac7-111">To add a label to a link</span></span>  
  
1.  <span data-ttu-id="8cac7-112">选择要标记的链接。</span><span class="sxs-lookup"><span data-stu-id="8cac7-112">Select the link you want to label.</span></span>  
  
2.  <span data-ttu-id="8cac7-113">在中**属性**窗口中，提供新的名称在**标签**字段。</span><span class="sxs-lookup"><span data-stu-id="8cac7-113">In the **Properties** window, provide the new name in the **Label** field.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="8cac7-114">最大允许的字符数为 256。</span><span class="sxs-lookup"><span data-stu-id="8cac7-114">The maximum number of characters allowed is 256.</span></span> <span data-ttu-id="8cac7-115">如果指定超过 256 个字符的字符串，则接受前 256 个字符，并丢弃剩余部分。</span><span class="sxs-lookup"><span data-stu-id="8cac7-115">If a string with more than 256 characters is specified, the first 256 characters are accepted and the rest are discarded.</span></span>  
  
     <span data-ttu-id="8cac7-116">![链接标签属性](../core/media/new-to-label-link.gif "New_To_Label_Link")</span><span class="sxs-lookup"><span data-stu-id="8cac7-116">![Link label properties](../core/media/new-to-label-link.gif "New_To_Label_Link")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8cac7-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="8cac7-117">See Also</span></span>  
 [<span data-ttu-id="8cac7-118">使用链接指定记录和字段映射</span><span class="sxs-lookup"><span data-stu-id="8cac7-118">Using Links to Specify Record and Field Mappings</span></span>](../core/using-links-to-specify-record-and-field-mappings.md)