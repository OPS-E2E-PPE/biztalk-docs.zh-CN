---
title: Oracle EBS 适配器客户端的功能 |Microsoft Docs
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
ms.openlocfilehash: 5378f72b9d3d0ff3343c17c68b9332d6e0adf8fa
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65375520"
---
# <a name="features-for-oracle-ebs-adapter-clients"></a><span data-ttu-id="123cf-102">Oracle EBS 适配器客户端的功能</span><span class="sxs-lookup"><span data-stu-id="123cf-102">Features for Oracle EBS adapter clients</span></span>
<span data-ttu-id="123cf-103">除了讨论的主题的功能[概述的 BizTalk 适配器用于 Oracle E-business Suite](http://msdn.microsoft.com/library/4f18fa2e-4e97-4c28-b38d-fc39ac53789e)，则[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]还提供了可用于适配器客户端的以下功能：</span><span class="sxs-lookup"><span data-stu-id="123cf-103">In addition to the features discussed throughout the topics of [Overview of BizTalk Adapter for Oracle E-Business Suite](http://msdn.microsoft.com/library/4f18fa2e-4e97-4c28-b38d-fc39ac53789e), the [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] also provides the following features that are useful for adapter clients:</span></span>  
  
- <span data-ttu-id="123cf-104">**配置使用绑定属性的适配器的支持**。</span><span class="sxs-lookup"><span data-stu-id="123cf-104">**Support for configuring adapters using binding properties**.</span></span> <span data-ttu-id="123cf-105">适配器客户端可以配置[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]通过指定特定绑定属性。</span><span class="sxs-lookup"><span data-stu-id="123cf-105">Adapter clients can configure the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] by specifying certain binding properties.</span></span> <span data-ttu-id="123cf-106">例如，客户端可以配置适配器后，通过设置使用 ODP.NET 连接池**UseOracleConnectionPool**属性绑定。</span><span class="sxs-lookup"><span data-stu-id="123cf-106">For example, clients can configure the adapter to use the ODP.NET connection pool by setting the **UseOracleConnectionPool** binding property.</span></span> <span data-ttu-id="123cf-107">有关详细信息，请参阅[了解关于 BizTalk Adapter for Oracle E-business Suite 绑定属性](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="123cf-107">For more information, see [Read about the BizTalk Adapter for Oracle E-Business Suite Binding Properties](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md).</span></span>  
  
- <span data-ttu-id="123cf-108">**操作参数的 null 值的支持**。</span><span class="sxs-lookup"><span data-stu-id="123cf-108">**Support for null values for operation parameters**.</span></span> <span data-ttu-id="123cf-109">适配器客户端可以为输入 XML 中使用"nil"属性的操作参数提供 null 值。</span><span class="sxs-lookup"><span data-stu-id="123cf-109">Adapter clients can provide null values for operation parameters using the “nil” attribute in the input XML.</span></span>  
  
- <span data-ttu-id="123cf-110">**支持在 BizTalk 中的动态端口**。</span><span class="sxs-lookup"><span data-stu-id="123cf-110">**Support for dynamic ports in BizTalk**.</span></span> <span data-ttu-id="123cf-111">通过 BizTalk [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)]，则[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]支持动态端口，使动态路由的消息从[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]基于消息上下文属性。</span><span class="sxs-lookup"><span data-stu-id="123cf-111">Through the BizTalk [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)], the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] supports a dynamic port that enables dynamic routing of messages from [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] based on the message context properties.</span></span> <span data-ttu-id="123cf-112">有关详细信息，请参阅[中的 SQL 适配器配置动态端口](../../adapters-and-accelerators/adapter-sql/configure-dynamic-ports-in-the-sql-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="123cf-112">For more information, see [Configure Dynamic Ports in the SQL adapter](../../adapters-and-accelerators/adapter-sql/configure-dynamic-ports-in-the-sql-adapter.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="123cf-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="123cf-113">See Also</span></span>  
[<span data-ttu-id="123cf-114">了解用于 Oracle E-Business Suite 的 BizTalk 适配器</span><span class="sxs-lookup"><span data-stu-id="123cf-114">Understand BizTalk Adapter for Oracle E-Business Suite</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/understand-biztalk-adapter-for-oracle-e-business-suite.md)