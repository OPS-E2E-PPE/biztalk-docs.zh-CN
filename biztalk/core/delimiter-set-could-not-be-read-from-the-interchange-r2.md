---
title: 无法读取分隔符集，从交换 (R2) |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 17bdd32e-d43f-4f59-af27-5d3054fd5432
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d3836b218ac3596bef25edb29eaf72c38f65b6e9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22239077"
---
# <a name="delimiter-set-could-not-be-read-from-the-interchange-r2"></a><span data-ttu-id="018c5-102">无法从交换 (R2) 读取分隔符集</span><span class="sxs-lookup"><span data-stu-id="018c5-102">Delimiter set could not be read from the interchange (R2)</span></span>
## <a name="details"></a><span data-ttu-id="018c5-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="018c5-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="018c5-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="018c5-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="018c5-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="018c5-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="018c5-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="018c5-106">Event ID</span></span>|-|  
|<span data-ttu-id="018c5-107">事件源</span><span class="sxs-lookup"><span data-stu-id="018c5-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="018c5-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="018c5-108"> EDI</span></span>|  
|<span data-ttu-id="018c5-109">组件</span><span class="sxs-lookup"><span data-stu-id="018c5-109">Component</span></span>|<span data-ttu-id="018c5-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="018c5-110">EDI Engine</span></span>|  
|<span data-ttu-id="018c5-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="018c5-111">Symbolic Name</span></span>|-|  
|<span data-ttu-id="018c5-112">消息正文</span><span class="sxs-lookup"><span data-stu-id="018c5-112">Message Text</span></span>|<span data-ttu-id="018c5-113">无法从交换中读取分隔符集。</span><span class="sxs-lookup"><span data-stu-id="018c5-113">Delimiter set could not be read from the interchange.</span></span> <span data-ttu-id="018c5-114">根节点中缺少属性 DelimiterSetSerializedData。</span><span class="sxs-lookup"><span data-stu-id="018c5-114">The attribute DelimiterSetSerializedData is missing from root node.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="018c5-115">解释</span><span class="sxs-lookup"><span data-stu-id="018c5-115">Explanation</span></span>  
 <span data-ttu-id="018c5-116">此错误表明交换不包含分隔符集值。</span><span class="sxs-lookup"><span data-stu-id="018c5-116">This error indicates the interchange does not contain the delimiter set values.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="018c5-117">用户操作</span><span class="sxs-lookup"><span data-stu-id="018c5-117">User Action</span></span>  
 <span data-ttu-id="018c5-118">若要解决此错误，请执行以下操作之一：</span><span class="sxs-lookup"><span data-stu-id="018c5-118">To resolve this error, do one of the following:</span></span>  
  
-   <span data-ttu-id="018c5-119">按照如下方式将分隔符集值添加到交换中：</span><span class="sxs-lookup"><span data-stu-id="018c5-119">Add delimiter set values to the interchange, as follows:</span></span>  
  
    1.  <span data-ttu-id="018c5-120">打开消息。</span><span class="sxs-lookup"><span data-stu-id="018c5-120">Open up the message.</span></span>  
  
    2.  <span data-ttu-id="018c5-121">确定交换中是否存在 UNA 段。</span><span class="sxs-lookup"><span data-stu-id="018c5-121">Determine whether there is a UNA segment in the interchange.</span></span> <span data-ttu-id="018c5-122">如果没有 UNA 段，请咨询合作伙伴以将 UNA 段添加到交换中。</span><span class="sxs-lookup"><span data-stu-id="018c5-122">If there is not a UNA segment, ask the partner to add the UNA segment to the interchange.</span></span>  
  
-   <span data-ttu-id="018c5-123">按照如下方式输入 EfactDelimiters 管道属性的分隔符值：</span><span class="sxs-lookup"><span data-stu-id="018c5-123">Enter the delimiter values to the EfactDelimiters pipeline property, as follows:</span></span>  
  
    1.  <span data-ttu-id="018c5-124">在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台中，右键单击使用你要设置其属性的管道的接收位置或发送端口。</span><span class="sxs-lookup"><span data-stu-id="018c5-124">In [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, right-click the receive location or send port using the pipeline that you want to set properties for.</span></span> <span data-ttu-id="018c5-125">单击 **“属性”**。</span><span class="sxs-lookup"><span data-stu-id="018c5-125">Click **Properties**.</span></span>  
  
    2.  <span data-ttu-id="018c5-126">单击你要设置其属性的管道旁的省略号按钮 (…)。</span><span class="sxs-lookup"><span data-stu-id="018c5-126">Click the ellipsis button (…) next to the pipeline that you want to set properties for.</span></span>  
  
    3.  <span data-ttu-id="018c5-127">输入以逗号分隔列表形式的 UNA 分隔符（对于 UNA1、UNA2、UNA3、UNA4、UNA5 和 UNA6）的值，根据需要更改默认值。</span><span class="sxs-lookup"><span data-stu-id="018c5-127">Enter values for the UNA delimiters as a comma-delimited list (for UNA1, UNA2, UNA3, UNA4, UNA5, and UNA6), changing the defaults as required.</span></span> <span data-ttu-id="018c5-128">默认值为，如下所示： 0x3A、 0x2B、 0x2C、 0x3F、 0x20、 0x27。</span><span class="sxs-lookup"><span data-stu-id="018c5-128">The defaults are as follows: 0x3A, 0x2B, 0x2C, 0x3F, 0x20, 0x27.</span></span>  
  
    4.  <span data-ttu-id="018c5-129">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="018c5-129">Click **OK**.</span></span>