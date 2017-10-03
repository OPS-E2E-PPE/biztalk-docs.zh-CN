---
title: "部署端口和 1> |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ports, deploying
- deployment, ports
- deployment, assemblies
- assemblies, deploying
ms.assetid: e259f7fe-c443-4015-a630-f08220e5437a
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cf2515cd5ee80f62a55e0b26b33bb93c3685ce6b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="deploying-ports-and-assemblies"></a><span data-ttu-id="03734-102">部署端口和程序集</span><span class="sxs-lookup"><span data-stu-id="03734-102">Deploying Ports and Assemblies</span></span>
<span data-ttu-id="03734-103">使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，可在目标计算机上复制端口和程序集。</span><span class="sxs-lookup"><span data-stu-id="03734-103">Using [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], you can duplicate ports and assemblies on a target computer.</span></span> <span data-ttu-id="03734-104">该向导将发送端口/接收位置配置导出到一个 XML 文件中。</span><span class="sxs-lookup"><span data-stu-id="03734-104">The wizard exports the send ports/receive location configuration into an XML file.</span></span>  
  
 <span data-ttu-id="03734-105">您可以使用 BizTalk Server 来执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="03734-105">You use BizTalk Server to do the following tasks:</span></span>  
  
-   <span data-ttu-id="03734-106">将 BizTalk Server 程序集部署到 BizTalk 配置数据库中或从其删除。</span><span class="sxs-lookup"><span data-stu-id="03734-106">Deploy or remove BizTalk Server assemblies in a BizTalk Configuration database.</span></span>  
  
-   <span data-ttu-id="03734-107">将程序集安装在全局程序集缓存 (GAC) 中或从其卸载。</span><span class="sxs-lookup"><span data-stu-id="03734-107">Install or uninstall the assemblies in the global assembly cache (GAC).</span></span>  
  
-   <span data-ttu-id="03734-108">将 BizTalk Server 程序集绑定信息导入到绑定文件或从其导出。</span><span class="sxs-lookup"><span data-stu-id="03734-108">Import or export BizTalk Server assembly binding information to and from binding files.</span></span>  
  
 <span data-ttu-id="03734-109">有关如何使用信息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]若要部署的端口和程序集，请参阅[如何导出 BizTalk 应用程序的绑定](../core/how-to-export-bindings-for-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="03734-109">For information about how to use [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to deploy ports and assemblies, see [How to Export Bindings for a BizTalk Application](../core/how-to-export-bindings-for-a-biztalk-application.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="03734-110">TIBCO Rendezvous 的 Microsoft BizTalk 适配器只要求在源（开发）计算机上具有 Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="03734-110">Microsoft BizTalk Adapter for TIBCO Rendezvous only requires that you have Visual Studio on a source (development) computer.</span></span> <span data-ttu-id="03734-111">在生产计算机上不要求使用 Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="03734-111">Visual Studio is not required on the production computer.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="03734-112">本节内容</span><span class="sxs-lookup"><span data-stu-id="03734-112">In This Section</span></span>  
  
-   [<span data-ttu-id="03734-113">验证部署安装</span><span class="sxs-lookup"><span data-stu-id="03734-113">Verifying the Deployment Setup</span></span>](../core/verifying-the-deployment-setup3.md)  
  
-   [<span data-ttu-id="03734-114">如何清洗目标计算机</span><span class="sxs-lookup"><span data-stu-id="03734-114">How to Clean the Target Computer</span></span>](../core/how-to-clean-the-target-computer1.md)