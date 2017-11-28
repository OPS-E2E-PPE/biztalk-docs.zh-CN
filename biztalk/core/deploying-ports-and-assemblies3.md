---
title: "部署端口和 Assemblies3 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ports, deploying
- Deployment Wizard
- assemblies, deploying
- deployment, ports and assemblies
ms.assetid: 92de8d9f-79d4-4c7a-a66a-12928bce350f
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3c37a677904143d4a925d035c409f485f43958ec
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="deploying-ports-and-assemblies"></a><span data-ttu-id="667e3-102">部署端口和程序集</span><span class="sxs-lookup"><span data-stu-id="667e3-102">Deploying Ports and Assemblies</span></span>
<span data-ttu-id="667e3-103">与[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，你可以复制端口和目标计算机上的程序集。</span><span class="sxs-lookup"><span data-stu-id="667e3-103">With [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], you can duplicate ports and assemblies on a target computer.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="667e3-104">发送/接收端口的位置将配置导出到 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="667e3-104"> exports the send ports/receive location configuration into an XML file.</span></span>  
  
 <span data-ttu-id="667e3-105">使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 可以执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="667e3-105">You can use [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to do the following tasks:</span></span>  
  
-   <span data-ttu-id="667e3-106">将 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 程序集部署到 BizTalk 配置数据库中或从其删除</span><span class="sxs-lookup"><span data-stu-id="667e3-106">Deploy or remove [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] assemblies in a BizTalk Configuration database</span></span>  
  
-   <span data-ttu-id="667e3-107">将程序集安装在全局程序集缓存 (GAC) 中或从其卸载</span><span class="sxs-lookup"><span data-stu-id="667e3-107">Install or uninstall the assemblies in the global assembly cache (GAC)</span></span>  
  
-   <span data-ttu-id="667e3-108">将 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 程序集绑定信息导入到绑定文件或从其导出</span><span class="sxs-lookup"><span data-stu-id="667e3-108">Import or export [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] assembly binding information to and from binding files</span></span>  
  
 <span data-ttu-id="667e3-109">有关如何使用信息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]若要部署的端口和程序集，请参阅[如何导出 BizTalk 应用程序的绑定](../core/how-to-export-bindings-for-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="667e3-109">For information about how to use [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to deploy ports and assemblies, see [How to Export Bindings for a BizTalk Application](../core/how-to-export-bindings-for-a-biztalk-application.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="667e3-110">用于 JD Edwards EnterpriseOne 的 Microsoft BizTalk 适配器只要求在源（开发）计算机上具有 Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="667e3-110">The Microsoft BizTalk Adapter for JD Edwards EnterpriseOne only requires that you have Visual Studio on a source (development) computer.</span></span> <span data-ttu-id="667e3-111">在生产计算机上不要求使用 Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="667e3-111">Visual Studio is not required on the production computer.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="667e3-112">本节内容</span><span class="sxs-lookup"><span data-stu-id="667e3-112">In This Section</span></span>  
  
-   [<span data-ttu-id="667e3-113">验证部署安装</span><span class="sxs-lookup"><span data-stu-id="667e3-113">Verifying the Deployment Setup</span></span>](../core/verifying-the-deployment-setup1.md)  
  
-   [<span data-ttu-id="667e3-114">导入绑定文件</span><span class="sxs-lookup"><span data-stu-id="667e3-114">Importing Binding Files</span></span>](../core/importing-binding-files2.md)  
  
-   [<span data-ttu-id="667e3-115">部署限制</span><span class="sxs-lookup"><span data-stu-id="667e3-115">Deployment Limitations</span></span>](../core/deployment-limitations4.md)