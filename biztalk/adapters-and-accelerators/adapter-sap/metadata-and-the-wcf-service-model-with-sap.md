---
title: "元数据和 WCF 服务模型与 SAP |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1900cf66-a0d0-46f4-896b-7f6de3b51875
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f06cd33c0776df70e5ff2554d355915908012abb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="metadata-and-the-wcf-service-model-with-sap"></a><span data-ttu-id="ebc56-102">元数据和 WCF 服务模型与 SAP</span><span class="sxs-lookup"><span data-stu-id="ebc56-102">Metadata and the WCF Service Model with SAP</span></span>
<span data-ttu-id="ebc56-103">在 WCF 服务模型中，你使用[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]或 ServiceModel 元数据实用工具 (svcutile.exe) 生成代理类通过其代码可以：</span><span class="sxs-lookup"><span data-stu-id="ebc56-103">In the WCF service model, you use the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)].or the ServiceModel Metadata Utility Tool (svcutile.exe) to generate proxy classes through which your code can either:</span></span>  
  
-   <span data-ttu-id="ebc56-104">调用适配器 （WCF 客户端类） 上的操作</span><span class="sxs-lookup"><span data-stu-id="ebc56-104">Invoke operations on the adapter (a WCF client class)</span></span>  
  
-   <span data-ttu-id="ebc56-105">从适配器 （WCF 服务协定） 接收操作</span><span class="sxs-lookup"><span data-stu-id="ebc56-105">Receive operations from the adapter (a WCF service contract)</span></span>  
  
 <span data-ttu-id="ebc56-106">这些工具生成表示服务协定的操作 （以及支持消息协定、 操作协定和数据协定） 的.NET 类公开的元数据从[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="ebc56-106">These tools generate .NET classes that represent a service contract for target operations (as well as the supporting message contracts, operation contracts, and data contracts) from the metadata exposed by the [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)].</span></span> <span data-ttu-id="ebc56-107">了解此生成的代码的结构的帮助，请参阅[了解生成的客户端代码](https://msdn.microsoft.com/library/ms733881.aspx)。</span><span class="sxs-lookup"><span data-stu-id="ebc56-107">For help in understanding the structure of this generated code, see [Understanding Generated Client Code](https://msdn.microsoft.com/library/ms733881.aspx).</span></span> <span data-ttu-id="ebc56-108">本主题专门介绍 svcutil.exe 生成，但其内容也是适用于代码的代码，[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]生成。</span><span class="sxs-lookup"><span data-stu-id="ebc56-108">This topic specifically describes code that svcutil.exe generates, but its content is also applicable to the code that the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] generates.</span></span> <span data-ttu-id="ebc56-109">有关如何生成 WCF 客户端类或 WCF 服务协定 （接口） 为目标操作以及 svcutil.exe 之间的差异信息和[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]，请参阅[为 SAP 生成 WCF 客户端或 WCF 服务协定解决方案项目](../../adapters-and-accelerators/adapter-sap/generate-a-wcf-client-or-a-wcf-service-contract-for-sap-solution-artifacts.md)。</span><span class="sxs-lookup"><span data-stu-id="ebc56-109">For information about how to generate a WCF client class or WCF service contract (interface) for target operations and about the differences between svcutil.exe and the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], see [Generate a WCF client or a WCF service contract for SAP solution artifacts](../../adapters-and-accelerators/adapter-sap/generate-a-wcf-client-or-a-wcf-service-contract-for-sap-solution-artifacts.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ebc56-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ebc56-110">See Also</span></span>  
[<span data-ttu-id="ebc56-111">开发使用 WCF 服务模型的 SAP 应用程序</span><span class="sxs-lookup"><span data-stu-id="ebc56-111">Develop SAP applications using the WCF Service Model</span></span>](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-service-model.md)