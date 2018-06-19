---
title: 元数据和 WCF 服务模型与 Siebel |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF service model, metadata
- metadata, and the WCF service model
ms.assetid: 3aca1835-fb9e-4841-a920-078da0b3fe76
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ed348c2ab183960b7af1383768259f67c4ca6270
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22221893"
---
# <a name="metadata-and-the-wcf-service-model-with-siebel"></a><span data-ttu-id="e19e7-102">元数据和 Siebel WCF 服务模型</span><span class="sxs-lookup"><span data-stu-id="e19e7-102">Metadata and the WCF Service Model with Siebel</span></span>
<span data-ttu-id="e19e7-103">在 WCF 服务模型中，你使用[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]或 ServiceModel 元数据实用工具 (svcutile.exe) 若要生成的代理类-WCF 客户端类 — 通过其代码可以调用操作上[!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="e19e7-103">In the WCF service model, you use the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] or the ServiceModel Metadata Utility Tool (svcutile.exe) to generate a proxy class—the WCF client class—through which your code can invoke operations on the [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)].</span></span>  
  
 <span data-ttu-id="e19e7-104">这些工具使用适配器公开的元数据来生成：</span><span class="sxs-lookup"><span data-stu-id="e19e7-104">These tools use the metadata exposed by the adapter to generate:</span></span>  
  
-   <span data-ttu-id="e19e7-105">表示目标操作的服务协定的.NET 批注的接口。</span><span class="sxs-lookup"><span data-stu-id="e19e7-105">An annotated .NET interface that represents the service contract for target operations.</span></span> <span data-ttu-id="e19e7-106">此接口称为 WCF 服务协定。</span><span class="sxs-lookup"><span data-stu-id="e19e7-106">This interface is called the WCF service contract.</span></span>  
  
-   <span data-ttu-id="e19e7-107">表示支持消息协定、 操作协定和服务协定的数据协定的带批注的类。</span><span class="sxs-lookup"><span data-stu-id="e19e7-107">Annotated classes that represent the supporting message contracts, operation contracts, and data contracts for the service contract.</span></span>  
  
-   <span data-ttu-id="e19e7-108">WCF 客户端类，可以使用其方法来调用由 WCF 服务协定公开的服务方法 （操作）。</span><span class="sxs-lookup"><span data-stu-id="e19e7-108">A WCF client class whose methods can be used to invoke the service methods (operations) exposed by the WCF service contract.</span></span>  
  
 <span data-ttu-id="e19e7-109">如需帮助了解此生成结构代码，请参阅"了解生成客户端代码"，网址[http://go.microsoft.com/fwlink/?LinkId=98365](http://go.microsoft.com/fwlink/?LinkId=98365)。</span><span class="sxs-lookup"><span data-stu-id="e19e7-109">For help in understanding the structure of this generated code, see "Understanding Generated Client Code" at [http://go.microsoft.com/fwlink/?LinkId=98365](http://go.microsoft.com/fwlink/?LinkId=98365).</span></span> <span data-ttu-id="e19e7-110">本主题专门介绍 svcutil.exe 生成，但其内容也是适用于代码的代码，[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]生成。</span><span class="sxs-lookup"><span data-stu-id="e19e7-110">This topic specifically describes code that svcutil.exe generates, but its content is also applicable to the code that the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] generates.</span></span>  
  
 <span data-ttu-id="e19e7-111">有关如何生成 WCF 客户端类，以便使用目标操作以及 svcutil.exe 之间的差异信息和[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]，请参阅[生成 WCF 客户端或 WCF 的服务协定为 Siebel 解决方案项目](../../adapters-and-accelerators/adapter-siebel/generate-a-wcf-client-or-a-wcf-service-contract-for-siebel-solution-artifacts.md)</span><span class="sxs-lookup"><span data-stu-id="e19e7-111">For information about how to generate a WCF client class for target operations and about the differences between svcutil.exe and the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], see [Generate a WCF Client or a WCF service contract for for Siebel solution Artifacts](../../adapters-and-accelerators/adapter-siebel/generate-a-wcf-client-or-a-wcf-service-contract-for-siebel-solution-artifacts.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e19e7-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e19e7-112">See Also</span></span>  
 [<span data-ttu-id="e19e7-113">开发 Siebel 应用程序使用 WCF 服务模型</span><span class="sxs-lookup"><span data-stu-id="e19e7-113">Develop Siebel applications using the WCF Service Model</span></span>](../../adapters-and-accelerators/adapter-siebel/develop-siebel-applications-using-the-wcf-service-model.md)