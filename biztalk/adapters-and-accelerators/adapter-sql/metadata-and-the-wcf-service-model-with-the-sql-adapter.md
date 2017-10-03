---
title: "元数据和 WCF 服务模型与 SQL 适配器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4353ce67-f0e8-4f96-b1d9-95deeee7f3e6
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c95ed3188c01f0f6d568bd745decd9e601e6ee3b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="metadata-and-the-wcf-service-model-with-the-sql-adapter"></a><span data-ttu-id="b0628-102">元数据和 WCF 服务模型与 SQL 适配器</span><span class="sxs-lookup"><span data-stu-id="b0628-102">Metadata and the WCF Service Model with the SQL adapter</span></span>
<span data-ttu-id="b0628-103">在 WCF 服务模型中，你使用[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]或 ServiceModel 元数据实用工具 (svcutile.exe) 来执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="b0628-103">In the WCF service model, you use the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] or the ServiceModel Metadata Utility Tool (svcutile.exe) to do the following:</span></span>  
  
-   <span data-ttu-id="b0628-104">生成服务协定 — WCF 服务协定-通过它你的代码可以从适配器接收操作。</span><span class="sxs-lookup"><span data-stu-id="b0628-104">Generate a service contract—the WCF service contract—through which your code can receive operations from the adapter.</span></span> <span data-ttu-id="b0628-105">此.NET 接口表示目标操作的服务协定。</span><span class="sxs-lookup"><span data-stu-id="b0628-105">This .NET interface represents the service contract for target operations.</span></span>  
  
-   <span data-ttu-id="b0628-106">生成代理类-WCF 客户端类-你的代码可以通过该调用在适配器上的操作。</span><span class="sxs-lookup"><span data-stu-id="b0628-106">Generate proxy classes—the WCF client class—through which your code can invoke operations on the adapter.</span></span>  
  
-   <span data-ttu-id="b0628-107">表示支持消息协定、 操作协定和服务协定的数据协定的带批注的类。</span><span class="sxs-lookup"><span data-stu-id="b0628-107">Annotated classes that represent the supporting message contracts, operation contracts, and data contracts for the service contract.</span></span>  
  
 <span data-ttu-id="b0628-108">了解此生成的代码的结构的帮助，请参阅[了解生成的客户端代码](https://msdn.microsoft.com/library/ms733881.aspx)。</span><span class="sxs-lookup"><span data-stu-id="b0628-108">For help in understanding the structure of this generated code, see [Understanding Generated Client Code](https://msdn.microsoft.com/library/ms733881.aspx).</span></span> <span data-ttu-id="b0628-109">本主题专门介绍 svcutil.exe 生成，但其内容也是适用于代码的代码，[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]生成。</span><span class="sxs-lookup"><span data-stu-id="b0628-109">This topic specifically describes code that svcutil.exe generates, but its content is also applicable to the code that the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] generates.</span></span>  
  
 <span data-ttu-id="b0628-110">有关如何生成 WCF 客户端类或 WCF 服务约定以目标操作以及 svcutil.exe 之间的差异信息和[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]，请参阅[为 SQL Server 项目生成 WCF 客户端或 WCF 服务协定](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md).</span><span class="sxs-lookup"><span data-stu-id="b0628-110">For information about how to generate a WCF client class or WCF service contract for target operations and about the differences between svcutil.exe and the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], see [Generate a WCF Client or WCF Service Contract for SQL Server Artifacts](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0628-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b0628-111">See Also</span></span>  
[<span data-ttu-id="b0628-112">开发 SQL 应用程序使用 WCF 服务模型</span><span class="sxs-lookup"><span data-stu-id="b0628-112">Develop SQL applications using the WCF Service model</span></span>](../../adapters-and-accelerators/adapter-sql/develop-sql-applications-using-the-wcf-service-model.md)