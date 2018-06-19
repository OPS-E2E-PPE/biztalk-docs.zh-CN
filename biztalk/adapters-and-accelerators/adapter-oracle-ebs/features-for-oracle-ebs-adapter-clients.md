---
title: 适用于 Oracle EBS 适配器客户端的功能 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 50256fb7-5f0c-4b32-87e6-98f49da0b360
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2da086390fe049a5333dda40a35e19f46298dda1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22217253"
---
# <a name="features-for-oracle-ebs-adapter-clients"></a><span data-ttu-id="716d1-102">适用于 Oracle EBS 适配器客户端的功能</span><span class="sxs-lookup"><span data-stu-id="716d1-102">Features for Oracle EBS adapter clients</span></span>
<span data-ttu-id="716d1-103">除了对在的主题中讨论的功能[概述的 BizTalk Adapter for Oracle E-business Suite](http://msdn.microsoft.com/library/4f18fa2e-4e97-4c28-b38d-fc39ac53789e)、[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]还提供了以下功能，可用于适配器客户端：</span><span class="sxs-lookup"><span data-stu-id="716d1-103">In addition to the features discussed throughout the topics of [Overview of BizTalk Adapter for Oracle E-Business Suite](http://msdn.microsoft.com/library/4f18fa2e-4e97-4c28-b38d-fc39ac53789e), the [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] also provides the following features that are useful for adapter clients:</span></span>  
  
-   <span data-ttu-id="716d1-104">**配置使用绑定属性的适配器的支持**。</span><span class="sxs-lookup"><span data-stu-id="716d1-104">**Support for configuring adapters using binding properties**.</span></span> <span data-ttu-id="716d1-105">适配器客户端可以配置[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]通过指定特定的绑定属性。</span><span class="sxs-lookup"><span data-stu-id="716d1-105">Adapter clients can configure the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] by specifying certain binding properties.</span></span> <span data-ttu-id="716d1-106">例如，客户端可以配置适配器后，以通过设置使用 ODP.NET 连接池**UseOracleConnectionPool**绑定属性。</span><span class="sxs-lookup"><span data-stu-id="716d1-106">For example, clients can configure the adapter to use the ODP.NET connection pool by setting the **UseOracleConnectionPool** binding property.</span></span> <span data-ttu-id="716d1-107">有关详细信息，请参阅[了解针对 Oracle E-business Suite 绑定属性的 BizTalk 适配器](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="716d1-107">For more information, see [Read about the BizTalk Adapter for Oracle E-Business Suite Binding Properties](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md).</span></span>  
  
-   <span data-ttu-id="716d1-108">**有关操作参数的 null 值的支持**。</span><span class="sxs-lookup"><span data-stu-id="716d1-108">**Support for null values for operation parameters**.</span></span> <span data-ttu-id="716d1-109">适配器客户端可以使用输入 XML 中的"nil"属性的操作参数提供 null 值。</span><span class="sxs-lookup"><span data-stu-id="716d1-109">Adapter clients can provide null values for operation parameters using the “nil” attribute in the input XML.</span></span>  
  
-   <span data-ttu-id="716d1-110">**BizTalk 中的动态端口支持**。</span><span class="sxs-lookup"><span data-stu-id="716d1-110">**Support for dynamic ports in BizTalk**.</span></span> <span data-ttu-id="716d1-111">通过 BizTalk [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)]、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]支持动态端口，使动态路由的消息从[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]基于消息上下文属性。</span><span class="sxs-lookup"><span data-stu-id="716d1-111">Through the BizTalk [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)], the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] supports a dynamic port that enables dynamic routing of messages from [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] based on the message context properties.</span></span> <span data-ttu-id="716d1-112">有关详细信息，请参阅[SQL 适配器中配置动态端口](../../adapters-and-accelerators/adapter-sql/configure-dynamic-ports-in-the-sql-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="716d1-112">For more information, see [Configure Dynamic Ports in the SQL adapter](../../adapters-and-accelerators/adapter-sql/configure-dynamic-ports-in-the-sql-adapter.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="716d1-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="716d1-113">See Also</span></span>  
[<span data-ttu-id="716d1-114">了解有关 Oracle E-business Suite 的 BizTalk Adapter</span><span class="sxs-lookup"><span data-stu-id="716d1-114">Understand BizTalk Adapter for Oracle E-Business Suite</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/understand-biztalk-adapter-for-oracle-e-business-suite.md)