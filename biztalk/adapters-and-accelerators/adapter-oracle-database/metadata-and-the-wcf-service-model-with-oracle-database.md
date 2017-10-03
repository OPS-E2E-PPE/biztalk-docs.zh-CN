---
title: "元数据和 WCF 服务与 Oracle 数据库的模型 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- service model, metadata
- WCF client class
- WCF service contract
ms.assetid: b55cf4ed-c41a-4986-bbaf-88e80c32b01f
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 76933dba64e6e8bb75eb0394ab8e6eedd3fb7116
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="metadata-and-the-wcf-service-model-with-oracle-database"></a><span data-ttu-id="357cf-102">元数据和 WCF 服务模型与 Oracle 数据库</span><span class="sxs-lookup"><span data-stu-id="357cf-102">Metadata and the WCF Service Model with Oracle Database</span></span>
<span data-ttu-id="357cf-103">在 WCF 服务模型中，你使用[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]或 ServiceModel 元数据实用工具 (svcutile.exe) 生成代理类通过其代码可以：</span><span class="sxs-lookup"><span data-stu-id="357cf-103">In the WCF service model, you use the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)].or the ServiceModel Metadata Utility Tool (svcutile.exe) to generate proxy classes through which your code can either:</span></span>  
  
-   <span data-ttu-id="357cf-104">调用适配器 （WCF 客户端类） 上的操作</span><span class="sxs-lookup"><span data-stu-id="357cf-104">Invoke operations on the adapter (a WCF client class)</span></span>  
  
-   <span data-ttu-id="357cf-105">从适配器 （WCF 服务协定） 接收操作</span><span class="sxs-lookup"><span data-stu-id="357cf-105">Receive operations from the adapter (a WCF service contract)</span></span>  
  
 <span data-ttu-id="357cf-106">这些工具生成表示服务协定的操作 （以及支持消息协定、 操作协定和数据协定） 的.NET 类公开的元数据从[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="357cf-106">These tools generate .NET classes that represent a service contract for target operations (as well as the supporting message contracts, operation contracts, and data contracts) from the metadata exposed by the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span> <span data-ttu-id="357cf-107">如需帮助了解此生成结构代码，请参阅"了解生成客户端代码"，网址[http://go.microsoft.com/fwlink/?LinkId=98365](http://go.microsoft.com/fwlink/?LinkId=98365)。</span><span class="sxs-lookup"><span data-stu-id="357cf-107">For help in understanding the structure of this generated code, see "Understanding Generated Client Code" at [http://go.microsoft.com/fwlink/?LinkId=98365](http://go.microsoft.com/fwlink/?LinkId=98365).</span></span> <span data-ttu-id="357cf-108">本主题专门介绍 svcutil.exe 生成，但其内容也是适用于代码的代码，[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]生成。</span><span class="sxs-lookup"><span data-stu-id="357cf-108">This topic specifically describes code that svcutil.exe generates, but its content is also applicable to the code that the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] generates.</span></span> <span data-ttu-id="357cf-109">有关如何生成 WCF 客户端类或 WCF 服务约定以目标操作以及 svcutil.exe 之间的差异信息和[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]，请参阅[为 Oracle 数据库生成 WCF 客户端或 WCF 服务协定解决方案项目](../../adapters-and-accelerators/adapter-oracle-database/create-a-wcf-client-or-wcf-service-contract-for-oracle-db-solution-artifacts.md)。</span><span class="sxs-lookup"><span data-stu-id="357cf-109">For information about how to generate a WCF client class or WCF service contract for target operations and about the differences between svcutil.exe and the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], see [Generate a WCF Client or a WCF Service Contract for Oracle Database Solution Artifacts](../../adapters-and-accelerators/adapter-oracle-database/create-a-wcf-client-or-wcf-service-contract-for-oracle-db-solution-artifacts.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="357cf-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="357cf-110">See Also</span></span>  
 [<span data-ttu-id="357cf-111">通过使用 WCF 服务模型开发 Oracle 数据库应用程序</span><span class="sxs-lookup"><span data-stu-id="357cf-111">Develop Oracle Database Applications by Using the WCF Service Model</span></span>](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-service-model.md)