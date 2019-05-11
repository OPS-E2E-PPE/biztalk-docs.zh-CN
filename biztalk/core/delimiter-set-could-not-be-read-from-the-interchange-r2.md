---
title: 无法从交换 (R2) 读取分隔符集 |Microsoft Docs
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
ms.openlocfilehash: 7208e9be2d8c5f28420151af060720f72eaa1913
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65390226"
---
# <a name="delimiter-set-could-not-be-read-from-the-interchange-r2"></a><span data-ttu-id="21246-102">无法从交换 (R2) 读取分隔符集</span><span class="sxs-lookup"><span data-stu-id="21246-102">Delimiter set could not be read from the interchange (R2)</span></span>
## <a name="details"></a><span data-ttu-id="21246-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="21246-103">Details</span></span>  

|                 |                                                                                                                           |
|-----------------|---------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="21246-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="21246-104">Product Name</span></span>   |                    [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                     |
| <span data-ttu-id="21246-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="21246-105">Product Version</span></span> |                                [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                 |
|    <span data-ttu-id="21246-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="21246-106">Event ID</span></span>     |                                                             -                                                             |
|  <span data-ttu-id="21246-107">事件源</span><span class="sxs-lookup"><span data-stu-id="21246-107">Event Source</span></span>   |                  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="21246-108">EDI</span><span class="sxs-lookup"><span data-stu-id="21246-108">EDI</span></span>                   |
|    <span data-ttu-id="21246-109">组件</span><span class="sxs-lookup"><span data-stu-id="21246-109">Component</span></span>    |                                                        <span data-ttu-id="21246-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="21246-110">EDI Engine</span></span>                                                         |
|  <span data-ttu-id="21246-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="21246-111">Symbolic Name</span></span>  |                                                             -                                                             |
|  <span data-ttu-id="21246-112">消息正文</span><span class="sxs-lookup"><span data-stu-id="21246-112">Message Text</span></span>   | <span data-ttu-id="21246-113">无法从交换读取分隔符集。</span><span class="sxs-lookup"><span data-stu-id="21246-113">Delimiter set could not be read from the interchange.</span></span> <span data-ttu-id="21246-114">从根节点缺少属性 DelimiterSetSerializedData。</span><span class="sxs-lookup"><span data-stu-id="21246-114">The attribute DelimiterSetSerializedData is missing from root node.</span></span> |

## <a name="explanation"></a><span data-ttu-id="21246-115">解释</span><span class="sxs-lookup"><span data-stu-id="21246-115">Explanation</span></span>  
 <span data-ttu-id="21246-116">此错误表明交换不包含分隔符集值。</span><span class="sxs-lookup"><span data-stu-id="21246-116">This error indicates the interchange does not contain the delimiter set values.</span></span>  

## <a name="user-action"></a><span data-ttu-id="21246-117">用户操作</span><span class="sxs-lookup"><span data-stu-id="21246-117">User Action</span></span>  
 <span data-ttu-id="21246-118">若要解决此错误，请执行以下操作之一：</span><span class="sxs-lookup"><span data-stu-id="21246-118">To resolve this error, do one of the following:</span></span>  

- <span data-ttu-id="21246-119">将分隔符集值添加到交换中，如下所示：</span><span class="sxs-lookup"><span data-stu-id="21246-119">Add delimiter set values to the interchange, as follows:</span></span>  

  1.  <span data-ttu-id="21246-120">打开消息。</span><span class="sxs-lookup"><span data-stu-id="21246-120">Open up the message.</span></span>  

  2.  <span data-ttu-id="21246-121">确定交换中是否存在 UNA 段。</span><span class="sxs-lookup"><span data-stu-id="21246-121">Determine whether there is a UNA segment in the interchange.</span></span> <span data-ttu-id="21246-122">如果不是 UNA 段，咨询合作伙伴以将 UNA 段添加到交换。</span><span class="sxs-lookup"><span data-stu-id="21246-122">If there is not a UNA segment, ask the partner to add the UNA segment to the interchange.</span></span>  

- <span data-ttu-id="21246-123">输入分隔符值 EfactDelimiters 管道属性，如下所示：</span><span class="sxs-lookup"><span data-stu-id="21246-123">Enter the delimiter values to the EfactDelimiters pipeline property, as follows:</span></span>  

  1. <span data-ttu-id="21246-124">在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击接收位置或发送端口使用你想要设置的属性的管道。</span><span class="sxs-lookup"><span data-stu-id="21246-124">In [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, right-click the receive location or send port using the pipeline that you want to set properties for.</span></span> <span data-ttu-id="21246-125">单击 **“属性”**。</span><span class="sxs-lookup"><span data-stu-id="21246-125">Click **Properties**.</span></span>  

  2. <span data-ttu-id="21246-126">单击你想要设置的属性的管道旁的省略号按钮 （...）。</span><span class="sxs-lookup"><span data-stu-id="21246-126">Click the ellipsis button (…) next to the pipeline that you want to set properties for.</span></span>  

  3. <span data-ttu-id="21246-127">输入值的 UNA 分隔符为逗号分隔列表 （UNA1、 UNA2、 UNA3、 UNA4、 UNA5 和 UNA6），更改所需的默认值。</span><span class="sxs-lookup"><span data-stu-id="21246-127">Enter values for the UNA delimiters as a comma-delimited list (for UNA1, UNA2, UNA3, UNA4, UNA5, and UNA6), changing the defaults as required.</span></span> <span data-ttu-id="21246-128">默认值如下所示：0x3A、 0x2B、 0x2C、 0x3F、 0x20、 0x27。</span><span class="sxs-lookup"><span data-stu-id="21246-128">The defaults are as follows: 0x3A, 0x2B, 0x2C, 0x3F, 0x20, 0x27.</span></span>  

  4. <span data-ttu-id="21246-129">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="21246-129">Click **OK**.</span></span>
