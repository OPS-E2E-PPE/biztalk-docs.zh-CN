---
title: 元数据和 WCF 服务模型与 Siebel |Microsoft Docs
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
ms.openlocfilehash: 73fdf3b57756bb2dfc007e63f803bf17c29285ab
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36976646"
---
# <a name="metadata-and-the-wcf-service-model-with-siebel"></a><span data-ttu-id="aff64-102">元数据和具有 Siebel 的 WCF 服务模型</span><span class="sxs-lookup"><span data-stu-id="aff64-102">Metadata and the WCF Service Model with Siebel</span></span>
<span data-ttu-id="aff64-103">在 WCF 服务模型，可使用[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]或 ServiceModel Metadata Utility Tool (svcutile.exe) 生成代理类，WCF 客户端类，通过该代码可以调用操作上[!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="aff64-103">In the WCF service model, you use the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] or the ServiceModel Metadata Utility Tool (svcutile.exe) to generate a proxy class—the WCF client class—through which your code can invoke operations on the [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)].</span></span>  
  
 <span data-ttu-id="aff64-104">这些工具使用由适配器公开的元数据来生成：</span><span class="sxs-lookup"><span data-stu-id="aff64-104">These tools use the metadata exposed by the adapter to generate:</span></span>  
  
- <span data-ttu-id="aff64-105">一个表示目标操作的服务协定的带批注的.NET 接口。</span><span class="sxs-lookup"><span data-stu-id="aff64-105">An annotated .NET interface that represents the service contract for target operations.</span></span> <span data-ttu-id="aff64-106">此接口被调用 WCF 服务约定。</span><span class="sxs-lookup"><span data-stu-id="aff64-106">This interface is called the WCF service contract.</span></span>  
  
- <span data-ttu-id="aff64-107">表示支持消息协定、 操作约定和服务协定的数据协定的带批注的类。</span><span class="sxs-lookup"><span data-stu-id="aff64-107">Annotated classes that represent the supporting message contracts, operation contracts, and data contracts for the service contract.</span></span>  
  
- <span data-ttu-id="aff64-108">WCF 客户端类的方法可用于调用服务方法 （操作） 公开的 WCF 服务约定。</span><span class="sxs-lookup"><span data-stu-id="aff64-108">A WCF client class whose methods can be used to invoke the service methods (operations) exposed by the WCF service contract.</span></span>  
  
  <span data-ttu-id="aff64-109">有关帮助理解此生成的结构代码，请参阅"了解生成客户端代码"，网址[ http://go.microsoft.com/fwlink/?LinkId=98365 ](http://go.microsoft.com/fwlink/?LinkId=98365)。</span><span class="sxs-lookup"><span data-stu-id="aff64-109">For help in understanding the structure of this generated code, see "Understanding Generated Client Code" at [http://go.microsoft.com/fwlink/?LinkId=98365](http://go.microsoft.com/fwlink/?LinkId=98365).</span></span> <span data-ttu-id="aff64-110">本主题专门介绍代码 svcutil.exe 生成，但其内容也是适用于代码的[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]生成。</span><span class="sxs-lookup"><span data-stu-id="aff64-110">This topic specifically describes code that svcutil.exe generates, but its content is also applicable to the code that the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] generates.</span></span>  
  
  <span data-ttu-id="aff64-111">有关如何生成目标的操作的 WCF 客户端类以及 svcutil.exe 之间的差异信息并[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]，请参阅[生成 WCF 客户端或 WCF 的服务约定以用于 Siebel 解决方案项目](../../adapters-and-accelerators/adapter-siebel/generate-a-wcf-client-or-a-wcf-service-contract-for-siebel-solution-artifacts.md)</span><span class="sxs-lookup"><span data-stu-id="aff64-111">For information about how to generate a WCF client class for target operations and about the differences between svcutil.exe and the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], see [Generate a WCF Client or a WCF service contract for for Siebel solution Artifacts](../../adapters-and-accelerators/adapter-siebel/generate-a-wcf-client-or-a-wcf-service-contract-for-siebel-solution-artifacts.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aff64-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="aff64-112">See Also</span></span>  
 [<span data-ttu-id="aff64-113">开发 Siebel 应用程序使用 WCF 服务模型</span><span class="sxs-lookup"><span data-stu-id="aff64-113">Develop Siebel applications using the WCF Service Model</span></span>](../../adapters-and-accelerators/adapter-siebel/develop-siebel-applications-using-the-wcf-service-model.md)