---
title: 为 Siebel eBusiness 应用程序的 BizTalk Adapter 概述 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- overview, adapter
- adapter, overview of
- adapter, overview
ms.assetid: 41ab7d42-7096-45ef-9763-a5ccf88eb652
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: efcc3a90f7025a5f396cd778676f5f3152bc7657
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22222037"
---
# <a name="overview-of-biztalk-adapter-for-siebel-ebusiness-applications"></a><span data-ttu-id="e1da1-102">为 Siebel eBusiness 应用程序的 BizTalk Adapter 概述</span><span class="sxs-lookup"><span data-stu-id="e1da1-102">Overview of BizTalk Adapter for Siebel eBusiness Applications</span></span>
<span data-ttu-id="e1da1-103">[!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]公开 Siebel 系统作为 WCF 服务。</span><span class="sxs-lookup"><span data-stu-id="e1da1-103">The [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)] exposes the Siebel system as a WCF service.</span></span> <span data-ttu-id="e1da1-104">适配器客户端可以通过交换 SOAP 消息与适配器执行 Siebel 系统上的操作。</span><span class="sxs-lookup"><span data-stu-id="e1da1-104">Adapter clients can perform operations on the Siebel system by exchanging SOAP messages with the adapter.</span></span> <span data-ttu-id="e1da1-105">适配器使用 WCF 消息，并且到 Siebel 系统的适当调用来执行该操作。</span><span class="sxs-lookup"><span data-stu-id="e1da1-105">The adapter consumes the WCF message and makes appropriate calls to the Siebel system to perform the operation.</span></span> <span data-ttu-id="e1da1-106">适配器回客户端的 SOAP 消息的形式，并将响应返回从 Siebel 系统。</span><span class="sxs-lookup"><span data-stu-id="e1da1-106">The adapter returns the response from the Siebel system back to the client in the form of SOAP messages.</span></span>  
  
 <span data-ttu-id="e1da1-107">[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]曲面 Siebel 项目 （业务服务中的业务组件） 的描述的元数据的结构的 SOAP 消息的 WSDL 形式。</span><span class="sxs-lookup"><span data-stu-id="e1da1-107">The [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] surfaces metadata of Siebel artifacts (business components, business services) that describes the structure of a SOAP message in the form of WSDL.</span></span> <span data-ttu-id="e1da1-108">[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]使用[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]和[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]才能使适配器客户端检索操作的元数据并在编程解决方案中生成可用的编程项目。</span><span class="sxs-lookup"><span data-stu-id="e1da1-108">The [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] uses the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] and [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] to enable adapter clients to retrieve metadata for operations and generates programming artifacts that can be used in your programming solution.</span></span>  
  
 <span data-ttu-id="e1da1-109">[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] Siebel COM 数据控件用于访问 Siebel 系统。</span><span class="sxs-lookup"><span data-stu-id="e1da1-109">The [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] uses the Siebel COM Data Control to access the Siebel system.</span></span> <span data-ttu-id="e1da1-110">Siebel COM 数据控件与 Siebel Web 客户端捆绑。</span><span class="sxs-lookup"><span data-stu-id="e1da1-110">The Siebel COM Data Control comes bundled with the Siebel Web client.</span></span> <span data-ttu-id="e1da1-111">因此，确保您具有相同的计算机上安装了 Siebel Web 客户端[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="e1da1-111">Hence, make sure you have the Siebel Web client installed on the same computer as the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].</span></span> <span data-ttu-id="e1da1-112">你可以使用[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]以下列方式与 Siebel 系统进行通信：</span><span class="sxs-lookup"><span data-stu-id="e1da1-112">You can use the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] to communicate with the Siebel system in the following ways:</span></span>  
  
-   <span data-ttu-id="e1da1-113">通过开发 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="e1da1-113">By developing BizTalk applications.</span></span> <span data-ttu-id="e1da1-114">请参阅[开发 BizTalk Server 应用程序](../../core/developing-biztalk-server-applications.md)。</span><span class="sxs-lookup"><span data-stu-id="e1da1-114">See [Developing BizTalk Server Applications](../../core/developing-biztalk-server-applications.md).</span></span>
  
-   <span data-ttu-id="e1da1-115">通过使用 WCF 服务模型。</span><span class="sxs-lookup"><span data-stu-id="e1da1-115">By using the WCF service model.</span></span> <span data-ttu-id="e1da1-116">请参阅[开发 Siebel 应用程序使用 WCF 服务模型](../../adapters-and-accelerators/adapter-siebel/develop-siebel-applications-using-the-wcf-service-model.md)。</span><span class="sxs-lookup"><span data-stu-id="e1da1-116">See [Develop Siebel Applications by Using the WCF Service Model](../../adapters-and-accelerators/adapter-siebel/develop-siebel-applications-using-the-wcf-service-model.md).</span></span>  
  
-   <span data-ttu-id="e1da1-117">通过使用 WCF 通道模型。</span><span class="sxs-lookup"><span data-stu-id="e1da1-117">By using the WCF channel model.</span></span> <span data-ttu-id="e1da1-118">请参阅开发 Oracle 数据库应用程序使用 WCF 通道模型[此处输入链接说明](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-channel-model.md)。</span><span class="sxs-lookup"><span data-stu-id="e1da1-118">See Develop Oracle Database Applications by Using the WCF Channel Model[enter link description here](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-channel-model.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e1da1-119">本节内容</span><span class="sxs-lookup"><span data-stu-id="e1da1-119">In This Section</span></span>  
  
-   <span data-ttu-id="e1da1-120">[适配器如何连接到 Siebel 系统？](https://msdn.microsoft.com/library/cc185212(v=bts.10).aspx)</span><span class="sxs-lookup"><span data-stu-id="e1da1-120">[How Does the Adapter Connect to a Siebel System?](https://msdn.microsoft.com/library/cc185212(v=bts.10).aspx)</span></span>  
  
-   <span data-ttu-id="e1da1-121">[原理适配器图面 Siebel 元数据是什么？](https://msdn.microsoft.com/library/cc185267(v=bts.10).aspx)</span><span class="sxs-lookup"><span data-stu-id="e1da1-121">[How Does the Adapter Surface Siebel Metadata?](https://msdn.microsoft.com/library/cc185267(v=bts.10).aspx)</span></span>  
  
-   <span data-ttu-id="e1da1-122">[哪些操作可以是执行使用适配器？](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)</span><span class="sxs-lookup"><span data-stu-id="e1da1-122">[What Operations Can be Performed Using the Adapter?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)</span></span>  
  
-   <span data-ttu-id="e1da1-123">[适配器支持的其他功能](https://msdn.microsoft.com/library/cc185252(v=bts.10).aspx)</span><span class="sxs-lookup"><span data-stu-id="e1da1-123">[Other Features Supported by the Adapter](https://msdn.microsoft.com/library/cc185252(v=bts.10).aspx)</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="e1da1-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e1da1-124">See Also</span></span>  
 [<span data-ttu-id="e1da1-125">为 Siebel eBusiness 应用程序了解的 BizTalk Adapter</span><span class="sxs-lookup"><span data-stu-id="e1da1-125">Understand BizTalk Adapter for Siebel eBusiness Applications</span></span>](../../adapters-and-accelerators/adapter-siebel/understand-biztalk-adapter-for-siebel-ebusiness-applications.md)