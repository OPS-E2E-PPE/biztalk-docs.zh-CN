---
title: "物理图 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: deploying, network configuration
ms.assetid: 4291727b-8687-496a-8f03-0da4b3201967
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0fcd0558d8fe3d45063a53800b1f3c082a2ba056
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="physical-diagram"></a><span data-ttu-id="7042e-102">物理关系图</span><span class="sxs-lookup"><span data-stu-id="7042e-102">Physical Diagram</span></span>
<span data-ttu-id="7042e-103">一个典型的部署具有聚集 BizTalk Server 计算机的消息 （发送和接收），用于执行业务流程 （业务流程），用于访问 InfoPath 模板 （MRSR 站点） 的 BizTalk Server 计算机的 BizTalk Server 计算机和群集的 SQL Server 计算机。</span><span class="sxs-lookup"><span data-stu-id="7042e-103">A typical deployment has clustered BizTalk Server computers for messaging (sending and receiving), BizTalk Server computers for executing the business process (orchestration), BizTalk Server computers for accessing the InfoPath templates (MRSR site), and clustered SQL Server computers.</span></span> <span data-ttu-id="7042e-104">以下部署可确保从 intranet 和 Internet 用户的安全环境。</span><span class="sxs-lookup"><span data-stu-id="7042e-104">The following deployment ensures a secure environment from both the intranet and Internet users.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7042e-105">此典型的部署是建议的配置。</span><span class="sxs-lookup"><span data-stu-id="7042e-105">This typical deployment is the recommended configuration.</span></span> <span data-ttu-id="7042e-106">你将需要验证你自己的业务需求和服务器配置，以确保你的部署正常运行。</span><span class="sxs-lookup"><span data-stu-id="7042e-106">You will need to verify your own business needs and server configurations to make certain your deployment works correctly.</span></span>  
  
 <span data-ttu-id="7042e-107">你可以扩展此部署向上或向下，out 或返回，具体取决于使用配置文件和不断增长的业务需求。</span><span class="sxs-lookup"><span data-stu-id="7042e-107">You can scale this deployment up or down, out or back, depending on the usage profile and your growing business needs.</span></span> <span data-ttu-id="7042e-108">典型的可伸缩性的方案包括在每个群集，以确保更高的可用性或更佳的吞吐量中添加一个或多个服务器。</span><span class="sxs-lookup"><span data-stu-id="7042e-108">Typical scalability scenarios include adding one or more servers in each cluster to ensure higher availability or better throughput.</span></span> <span data-ttu-id="7042e-109">较小的企业可能更喜欢缩减回其部署具有相同的服务器执行多项功能，如具有一个[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]计算机处理业务流程和消息传送。</span><span class="sxs-lookup"><span data-stu-id="7042e-109">Smaller enterprises might prefer scaling back their deployment to have the same servers perform multiple functions, such as having one [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] computer handle both orchestration and messaging.</span></span> [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]<span data-ttu-id="7042e-110">[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]支持一台服务器上的部署。</span><span class="sxs-lookup"><span data-stu-id="7042e-110">[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] supports deployment on a single server.</span></span> <span data-ttu-id="7042e-111">下图显示完整的 A4SWIFT 部署的建议的分布式的部署环境的示例。</span><span class="sxs-lookup"><span data-stu-id="7042e-111">The following figure shows an example of the recommended distributed deployment environment for a full A4SWIFT deployment.</span></span>  
  
 ![](../../adapters-and-accelerators/accelerator-swift/media/fsa-deploy-full.gif "FSA_Deploy_Full")  
<span data-ttu-id="7042e-112">完整的 A4SWIFT 部署示例</span><span class="sxs-lookup"><span data-stu-id="7042e-112">Example of a full A4SWIFT deployment</span></span>