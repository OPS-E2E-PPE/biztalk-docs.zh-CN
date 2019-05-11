---
title: Windows Communication Foundation 中的操作 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a1728d2f-ac74-446e-a36f-4b645a6e042a
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f43e6eb64e73c072830072a1fdd11dcefef25e32
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65263035"
---
# <a name="operations-in-windows-communication-foundation"></a><span data-ttu-id="dec22-102">Windows Communication Foundation 中的操作</span><span class="sxs-lookup"><span data-stu-id="dec22-102">Operations in Windows Communication Foundation</span></span>
<span data-ttu-id="dec22-103">本部分包含 BAM WCF 侦听器支持的自定义操作。</span><span class="sxs-lookup"><span data-stu-id="dec22-103">This section contains the custom operations supported by the BAM WCF interceptor.</span></span>  
  
 <span data-ttu-id="dec22-104">请注意，如果操作名称元素包含 Action 属性：</span><span class="sxs-lookup"><span data-stu-id="dec22-104">Note that if an operation name element contains an Action attribute:</span></span>  
  
1.  <span data-ttu-id="dec22-105">操作名称是由 name 属性标识的客户端和服务器，</span><span class="sxs-lookup"><span data-stu-id="dec22-105">The operation name is the one identified by the name attribute for both the client and the server,</span></span>  
  
2.  <span data-ttu-id="dec22-106">对于答复路径 （回调答复），客户端答复和服务答复，操作名称由 name 属性标识。</span><span class="sxs-lookup"><span data-stu-id="dec22-106">For reply paths (callback reply), client reply and service rely, the operation name is identified by the name attribute.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dec22-107">答复消息有一个节点将名为后面附加单词"Result"由 name 属性指定的名称。</span><span class="sxs-lookup"><span data-stu-id="dec22-107">Reply messages will have a node that is named by appending the word "Result" to the name specified by the name attribute.</span></span> <span data-ttu-id="dec22-108">您必须确保 xpaths 遵从此命名约定。</span><span class="sxs-lookup"><span data-stu-id="dec22-108">You must ensure that the XPaths reflect this naming convention.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="dec22-109">本节内容</span><span class="sxs-lookup"><span data-stu-id="dec22-109">In This Section</span></span>  
  
-   [<span data-ttu-id="dec22-110">AutoGenerateCorrelationToken</span><span class="sxs-lookup"><span data-stu-id="dec22-110">AutoGenerateCorrelationToken</span></span>](../core/autogeneratecorrelationtoken.md)  
  
-   [<span data-ttu-id="dec22-111">GetContextProperty</span><span class="sxs-lookup"><span data-stu-id="dec22-111">GetContextProperty</span></span>](../core/getcontextproperty1.md)  
  
-   [<span data-ttu-id="dec22-112">GetEndpointName</span><span class="sxs-lookup"><span data-stu-id="dec22-112">GetEndpointName</span></span>](../core/getendpointname.md)  
  
-   [<span data-ttu-id="dec22-113">GetOperationName</span><span class="sxs-lookup"><span data-stu-id="dec22-113">GetOperationName</span></span>](../core/getoperationname.md)  
  
-   [<span data-ttu-id="dec22-114">GetServiceContractCallPoint</span><span class="sxs-lookup"><span data-stu-id="dec22-114">GetServiceContractCallPoint</span></span>](../core/getservicecontractcallpoint.md)  
  
-   [<span data-ttu-id="dec22-115">XPath</span><span class="sxs-lookup"><span data-stu-id="dec22-115">XPath</span></span>](../core/xpath.md)