---
title: 元数据和 WCF 服务模型与 Oracle E-business Suite |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 95d3fcba-c72f-4ae9-82bd-abbfc2a0c2c4
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d7c076d13e0adc32352c85901541d2be46b5fcd2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36997838"
---
# <a name="metadata-and-the-wcf-service-model-with-oracle-e-business-suite"></a><span data-ttu-id="2c0e9-102">元数据和具有 Oracle E-business Suite 的 WCF 服务模型</span><span class="sxs-lookup"><span data-stu-id="2c0e9-102">Metadata and the WCF Service Model with Oracle E-Business Suite</span></span>
<span data-ttu-id="2c0e9-103">在 WCF 服务模型，可使用[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]或 ServiceModel Metadata Utility Tool (svcutile.exe) 来执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="2c0e9-103">In the WCF service model, you use the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] or the ServiceModel Metadata Utility Tool (svcutile.exe) to do the following:</span></span>  
  
- <span data-ttu-id="2c0e9-104">生成服务协定，WCF 服务约定，通过该代码可以从适配器接收操作。</span><span class="sxs-lookup"><span data-stu-id="2c0e9-104">Generate a service contract—the WCF service contract—through which your code can receive operations from the adapter.</span></span> <span data-ttu-id="2c0e9-105">此.NET 接口表示目标操作的服务协定。</span><span class="sxs-lookup"><span data-stu-id="2c0e9-105">This .NET interface represents the service contract for target operations.</span></span>  
  
- <span data-ttu-id="2c0e9-106">生成代理类，WCF 客户端类，通过该代码可以调用在适配器上的操作。</span><span class="sxs-lookup"><span data-stu-id="2c0e9-106">Generate proxy classes—the WCF client class—through which your code can invoke operations on the adapter.</span></span>  
  
- <span data-ttu-id="2c0e9-107">表示支持消息协定、 操作约定和服务协定的数据协定的带批注的类。</span><span class="sxs-lookup"><span data-stu-id="2c0e9-107">Annotated classes that represent the supporting message contracts, operation contracts, and data contracts for the service contract.</span></span>  
  
  <span data-ttu-id="2c0e9-108">有关帮助理解此生成的结构代码，请参阅"了解生成客户端代码"，网址[ http://go.microsoft.com/fwlink/?LinkId=98365 ](http://go.microsoft.com/fwlink/?LinkId=98365)。</span><span class="sxs-lookup"><span data-stu-id="2c0e9-108">For help in understanding the structure of this generated code, see "Understanding Generated Client Code" at [http://go.microsoft.com/fwlink/?LinkId=98365](http://go.microsoft.com/fwlink/?LinkId=98365).</span></span> <span data-ttu-id="2c0e9-109">本主题专门介绍代码 svcutil.exe 生成，但其内容也是适用于代码的[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]生成。</span><span class="sxs-lookup"><span data-stu-id="2c0e9-109">This topic specifically describes code that svcutil.exe generates, but its content is also applicable to the code that the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] generates.</span></span>  
  
  <span data-ttu-id="2c0e9-110">有关如何生成 WCF 客户端类或目标的操作的 WCF 服务协定和 svcutil.exe 之间的差异信息并[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]，请参阅[生成 WCF 客户端或 WCF 服务协定用于 Oracle E-business套件解决方案项目](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-wcf-client-or-wcf-service-contract-for-oracle-ebs-solution-artifacts.md)。</span><span class="sxs-lookup"><span data-stu-id="2c0e9-110">For information about how to generate a WCF client class or WCF service contract for target operations and about the differences between svcutil.exe and the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], see [Generate a WCF Client or a WCF Service Contract for Oracle E-Business Suite Solution Artifacts](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-wcf-client-or-wcf-service-contract-for-oracle-ebs-solution-artifacts.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c0e9-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="2c0e9-111">See Also</span></span>  
 [<span data-ttu-id="2c0e9-112">使用 WCF 服务模型开发 Oracle E-business Suite 应用程序</span><span class="sxs-lookup"><span data-stu-id="2c0e9-112">Develop Oracle E-Business Suite Applications by Using the WCF service Model</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/develop-oracle-e-business-suite-applications-using-the-wcf-service-model.md)