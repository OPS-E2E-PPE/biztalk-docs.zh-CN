---
title: "部署端口和 Assemblies5 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ports, deploying
- assemblies, deploying
- deployment, ports and assemblies
ms.assetid: 11d980c4-2502-4da2-b505-d7326aae619a
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 31df94e2a659fa29e6f21d2bd705de31da3c6b9a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="deploying-ports-and-assemblies"></a><span data-ttu-id="b9104-102">部署端口和程序集</span><span class="sxs-lookup"><span data-stu-id="b9104-102">Deploying Ports and Assemblies</span></span>
<span data-ttu-id="b9104-103">使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，可在目标计算机上复制端口和程序集。</span><span class="sxs-lookup"><span data-stu-id="b9104-103">Using [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], you can duplicate ports and assemblies on a target computer.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="b9104-104">发送/接收端口的位置将配置导出到 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="b9104-104"> exports the send ports/receive location configuration into an XML file.</span></span>  
  
 <span data-ttu-id="b9104-105">您可使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 执行下列任务：</span><span class="sxs-lookup"><span data-stu-id="b9104-105">You use the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to perform these tasks:</span></span>  
  
-   <span data-ttu-id="b9104-106">将 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 程序集部署到 BizTalk 配置数据库中或从其中删除。</span><span class="sxs-lookup"><span data-stu-id="b9104-106">Deploy or remove [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] assemblies in a BizTalk Configuration database.</span></span>  
  
-   <span data-ttu-id="b9104-107">将程序集安装在全局程序集缓存 (GAC) 中或从其卸载。</span><span class="sxs-lookup"><span data-stu-id="b9104-107">Install or uninstall the assemblies in the global assembly cache (GAC).</span></span>  
  
-   <span data-ttu-id="b9104-108">将 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 程序集绑定信息导入到绑定文件或从其中导出。</span><span class="sxs-lookup"><span data-stu-id="b9104-108">Import or export [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] assembly binding information to and from binding files.</span></span>  
  
 <span data-ttu-id="b9104-109">有关如何使用信息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]若要部署的端口和程序集，请参阅[如何导出 BizTalk 应用程序的绑定](../core/how-to-export-bindings-for-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="b9104-109">For information about how to use [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to deploy ports and assemblies, see [How to Export Bindings for a BizTalk Application](../core/how-to-export-bindings-for-a-biztalk-application.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b9104-110">Microsoft BizTalk Adapter for PeopleSoft 企业仅需要源 （开发） 计算机上安装 Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="b9104-110">The Microsoft BizTalk Adapter for PeopleSoft Enterprise only requires that you have Visual Studio on a source (development) computer.</span></span> <span data-ttu-id="b9104-111">在生产计算机上不要求使用 Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="b9104-111">Visual Studio is not required on the production computer.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b9104-112">本节内容</span><span class="sxs-lookup"><span data-stu-id="b9104-112">In This Section</span></span>  
  
-   [<span data-ttu-id="b9104-113">导入绑定文件</span><span class="sxs-lookup"><span data-stu-id="b9104-113">Importing Binding Files</span></span>](../core/importing-binding-files1.md)  
  
-   [<span data-ttu-id="b9104-114">部署限制</span><span class="sxs-lookup"><span data-stu-id="b9104-114">Deployment Limitations</span></span>](../core/deployment-limitations3.md)