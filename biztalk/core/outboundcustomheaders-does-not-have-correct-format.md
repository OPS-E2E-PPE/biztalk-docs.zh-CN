---
title: OutboundCustomHeaders 不具有正确的格式 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6097762b-01c9-48b8-8cee-ccd6b11d28d4
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6d9cb9311015bfa7d88169944a206a8882b11cfe
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37008918"
---
# <a name="outboundcustomheaders-does-not-have-correct-format"></a><span data-ttu-id="ddc78-102">OutboundCustomHeaders 不具有正确的格式</span><span class="sxs-lookup"><span data-stu-id="ddc78-102">OutboundCustomHeaders does not have correct format</span></span>
## <a name="details"></a><span data-ttu-id="ddc78-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="ddc78-103">Details</span></span>  
  
|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  <span data-ttu-id="ddc78-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="ddc78-104">Product Name</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| <span data-ttu-id="ddc78-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="ddc78-105">Product Version</span></span> |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    <span data-ttu-id="ddc78-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="ddc78-106">Event ID</span></span>     |                                         <span data-ttu-id="ddc78-107">0</span><span class="sxs-lookup"><span data-stu-id="ddc78-107">0</span></span>                                          |
|  <span data-ttu-id="ddc78-108">事件源</span><span class="sxs-lookup"><span data-stu-id="ddc78-108">Event Source</span></span>   |                                         <span data-ttu-id="ddc78-109">0</span><span class="sxs-lookup"><span data-stu-id="ddc78-109">0</span></span>                                          |
|    <span data-ttu-id="ddc78-110">组件</span><span class="sxs-lookup"><span data-stu-id="ddc78-110">Component</span></span>    |                                         <span data-ttu-id="ddc78-111">0</span><span class="sxs-lookup"><span data-stu-id="ddc78-111">0</span></span>                                          |
|  <span data-ttu-id="ddc78-112">符号名称</span><span class="sxs-lookup"><span data-stu-id="ddc78-112">Symbolic Name</span></span>  |                                         <span data-ttu-id="ddc78-113">0</span><span class="sxs-lookup"><span data-stu-id="ddc78-113">0</span></span>                                          |
|  <span data-ttu-id="ddc78-114">消息正文</span><span class="sxs-lookup"><span data-stu-id="ddc78-114">Message Text</span></span>   |                <span data-ttu-id="ddc78-115">OutboundCustomHeaders 的格式不正确</span><span class="sxs-lookup"><span data-stu-id="ddc78-115">OutboundCustomHeaders does not have a correct format</span></span>                |
  
## <a name="explanation"></a><span data-ttu-id="ddc78-116">解释</span><span class="sxs-lookup"><span data-stu-id="ddc78-116">Explanation</span></span>  
 <span data-ttu-id="ddc78-117">WCF 的值。InboundHeaders 或 WCF。OutboundCustomHeaders 不是采用以下格式：\<标头\>...\</headers\>。</span><span class="sxs-lookup"><span data-stu-id="ddc78-117">The value of WCF.InboundHeaders or WCF.OutboundCustomHeaders  is not in the following format: \<headers\>….\</headers\>.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="ddc78-118">用户操作</span><span class="sxs-lookup"><span data-stu-id="ddc78-118">User Action</span></span>  
 <span data-ttu-id="ddc78-119">包装属性值替换\<标头\>元素。</span><span class="sxs-lookup"><span data-stu-id="ddc78-119">Wrap the property values with \<headers\> element.</span></span>  
  
 <span data-ttu-id="ddc78-120">有关详细信息，请参阅中的以下资源[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助：</span><span class="sxs-lookup"><span data-stu-id="ddc78-120">For further information, see the following resource in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="ddc78-121">通过管道组件使用 WCF 消息中的 SOAP 标头</span><span class="sxs-lookup"><span data-stu-id="ddc78-121">Using SOAP Headers in WCF Messages with Pipeline Components</span></span>](../core/using-soap-headers-in-wcf-messages-with-pipeline-components.md)