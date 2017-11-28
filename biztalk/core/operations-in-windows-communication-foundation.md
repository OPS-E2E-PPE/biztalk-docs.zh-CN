---
title: "Windows Communication Foundation 中的操作 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a1728d2f-ac74-446e-a36f-4b645a6e042a
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7c6b5344b8fb2c5a5ba7a68b112adb50133198c3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="operations-in-windows-communication-foundation"></a><span data-ttu-id="a7e4f-102">Windows Communication Foundation 中的操作</span><span class="sxs-lookup"><span data-stu-id="a7e4f-102">Operations in Windows Communication Foundation</span></span>
<span data-ttu-id="a7e4f-103">本部分包含 BAM WCF 侦听器支持的自定义操作。</span><span class="sxs-lookup"><span data-stu-id="a7e4f-103">This section contains the custom operations supported by the BAM WCF interceptor.</span></span>  
  
 <span data-ttu-id="a7e4f-104">注意，如果操作名称元素包含 Action 属性：</span><span class="sxs-lookup"><span data-stu-id="a7e4f-104">Note that if an operation name element contains an Action attribute:</span></span>  
  
1.  <span data-ttu-id="a7e4f-105">操作名称是由客户端和服务器的名称属性共同标识的。</span><span class="sxs-lookup"><span data-stu-id="a7e4f-105">The operation name is the one identified by the name attribute for both the client and the server,</span></span>  
  
2.  <span data-ttu-id="a7e4f-106">对于答复路径（回调答复）、客户端答复和服务答复，操作名称由 name 属性标识。</span><span class="sxs-lookup"><span data-stu-id="a7e4f-106">For reply paths (callback reply), client reply and service rely, the operation name is identified by the name attribute.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a7e4f-107">答复消息中有一个节点将通过在由 name 属性指定的名称后面附加单词“Result”来命名。</span><span class="sxs-lookup"><span data-stu-id="a7e4f-107">Reply messages will have a node that is named by appending the word "Result" to the name specified by the name attribute.</span></span> <span data-ttu-id="a7e4f-108">您必须确保 XPaths 遵从此命名约定。</span><span class="sxs-lookup"><span data-stu-id="a7e4f-108">You must ensure that the XPaths reflect this naming convention.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a7e4f-109">本节内容</span><span class="sxs-lookup"><span data-stu-id="a7e4f-109">In This Section</span></span>  
  
-   [<span data-ttu-id="a7e4f-110">AutoGenerateCorrelationToken</span><span class="sxs-lookup"><span data-stu-id="a7e4f-110">AutoGenerateCorrelationToken</span></span>](../core/autogeneratecorrelationtoken.md)  
  
-   [<span data-ttu-id="a7e4f-111">GetContextProperty</span><span class="sxs-lookup"><span data-stu-id="a7e4f-111">GetContextProperty</span></span>](../core/getcontextproperty1.md)  
  
-   [<span data-ttu-id="a7e4f-112">GetEndpointName</span><span class="sxs-lookup"><span data-stu-id="a7e4f-112">GetEndpointName</span></span>](../core/getendpointname.md)  
  
-   [<span data-ttu-id="a7e4f-113">GetOperationName</span><span class="sxs-lookup"><span data-stu-id="a7e4f-113">GetOperationName</span></span>](../core/getoperationname.md)  
  
-   [<span data-ttu-id="a7e4f-114">GetServiceContractCallPoint</span><span class="sxs-lookup"><span data-stu-id="a7e4f-114">GetServiceContractCallPoint</span></span>](../core/getservicecontractcallpoint.md)  
  
-   [<span data-ttu-id="a7e4f-115">XPath</span><span class="sxs-lookup"><span data-stu-id="a7e4f-115">XPath</span></span>](../core/xpath.md)