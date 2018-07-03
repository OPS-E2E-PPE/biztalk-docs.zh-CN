---
title: 元数据和 WCF 服务模型使用 SAP |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1900cf66-a0d0-46f4-896b-7f6de3b51875
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8e4a3ca75470192f2237cf67c6ac0312b150b46a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36972830"
---
# <a name="metadata-and-the-wcf-service-model-with-sap"></a><span data-ttu-id="96bd5-102">元数据和具有 SAP 的 WCF 服务模型</span><span class="sxs-lookup"><span data-stu-id="96bd5-102">Metadata and the WCF Service Model with SAP</span></span>
<span data-ttu-id="96bd5-103">在 WCF 服务模型，可使用[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]或 ServiceModel Metadata Utility Tool (svcutile.exe) 生成代理类通过它你代码可能是：</span><span class="sxs-lookup"><span data-stu-id="96bd5-103">In the WCF service model, you use the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)].or the ServiceModel Metadata Utility Tool (svcutile.exe) to generate proxy classes through which your code can either:</span></span>  
  
- <span data-ttu-id="96bd5-104">调用适配器 （WCF 客户端类） 上的操作</span><span class="sxs-lookup"><span data-stu-id="96bd5-104">Invoke operations on the adapter (a WCF client class)</span></span>  
  
- <span data-ttu-id="96bd5-105">从适配器 （WCF 服务约定） 接收操作</span><span class="sxs-lookup"><span data-stu-id="96bd5-105">Receive operations from the adapter (a WCF service contract)</span></span>  
  
  <span data-ttu-id="96bd5-106">这些工具生成表示目标操作 （以及支持消息协定、 操作约定和数据协定） 的服务约定的.NET 类公开的元数据从[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="96bd5-106">These tools generate .NET classes that represent a service contract for target operations (as well as the supporting message contracts, operation contracts, and data contracts) from the metadata exposed by the [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)].</span></span> <span data-ttu-id="96bd5-107">了解此生成的代码的结构的帮助，请参阅[了解生成的客户端代码](https://msdn.microsoft.com/library/ms733881.aspx)。</span><span class="sxs-lookup"><span data-stu-id="96bd5-107">For help in understanding the structure of this generated code, see [Understanding Generated Client Code](https://msdn.microsoft.com/library/ms733881.aspx).</span></span> <span data-ttu-id="96bd5-108">本主题专门介绍代码 svcutil.exe 生成，但其内容也是适用于代码的[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]生成。</span><span class="sxs-lookup"><span data-stu-id="96bd5-108">This topic specifically describes code that svcutil.exe generates, but its content is also applicable to the code that the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] generates.</span></span> <span data-ttu-id="96bd5-109">有关如何生成 WCF 客户端类或 WCF 服务协定 （接口） 为目标的操作以及 svcutil.exe 之间的差异信息并[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]，请参阅[为 SAP 生成 WCF 客户端或 WCF 服务约定解决方案项目](../../adapters-and-accelerators/adapter-sap/generate-a-wcf-client-or-a-wcf-service-contract-for-sap-solution-artifacts.md)。</span><span class="sxs-lookup"><span data-stu-id="96bd5-109">For information about how to generate a WCF client class or WCF service contract (interface) for target operations and about the differences between svcutil.exe and the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], see [Generate a WCF client or a WCF service contract for SAP solution artifacts](../../adapters-and-accelerators/adapter-sap/generate-a-wcf-client-or-a-wcf-service-contract-for-sap-solution-artifacts.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96bd5-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="96bd5-110">See Also</span></span>  
[<span data-ttu-id="96bd5-111">开发 SAP 应用程序使用 WCF 服务模型</span><span class="sxs-lookup"><span data-stu-id="96bd5-111">Develop SAP applications using the WCF Service Model</span></span>](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-service-model.md)