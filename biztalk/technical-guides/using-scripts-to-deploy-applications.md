---
title: "使用脚本来部署应用程序 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9e683c5f-7576-4382-9952-d577cd00186c
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4566a810489a9f6c46424a525908aa5a2fbb6bee
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="using-scripts-to-deploy-applications"></a><span data-ttu-id="49bef-102">使用脚本来部署应用程序</span><span class="sxs-lookup"><span data-stu-id="49bef-102">Using Scripts to Deploy Applications</span></span>
<span data-ttu-id="49bef-103">您应使用脚本来部署 BizTalk 应用程序，在可能的情况。</span><span class="sxs-lookup"><span data-stu-id="49bef-103">You should use scripts to deploy BizTalk applications where possible.</span></span> <span data-ttu-id="49bef-104">脚本在部署过程中减少人为错误的风险。</span><span class="sxs-lookup"><span data-stu-id="49bef-104">Scripting reduces the risk of human error during the deployment process.</span></span> <span data-ttu-id="49bef-105">你应记录中深度你部署过程。</span><span class="sxs-lookup"><span data-stu-id="49bef-105">You should also document your deployment procedures in depth.</span></span> <span data-ttu-id="49bef-106">你应该记录你不具有非常详细步骤编写脚本的任何内容。</span><span class="sxs-lookup"><span data-stu-id="49bef-106">You should document anything that you do not script with very detailed steps.</span></span> <span data-ttu-id="49bef-107">这包括记录对外部系统和非 Microsoft 组件部署任何更改。</span><span class="sxs-lookup"><span data-stu-id="49bef-107">This includes documenting any changes to external systems and to deployment of non-Microsoft components.</span></span>  
  
## <a name="using-btstask"></a><span data-ttu-id="49bef-108">使用 BTSTask</span><span class="sxs-lookup"><span data-stu-id="49bef-108">Using BTSTask</span></span>  
 <span data-ttu-id="49bef-109">你可以使用 BTSTask.exe 编写脚本的 BizTalk 应用程序，以及有关导入现有创建[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].msi 包。</span><span class="sxs-lookup"><span data-stu-id="49bef-109">You can use BTSTask.exe to script the creation of BizTalk applications, as well as to import existing [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] .msi packages.</span></span> <span data-ttu-id="49bef-110">如果应用程序的创建已编写脚本，然后包可以自动生成的生成服务器上使用一个自动化的过程。</span><span class="sxs-lookup"><span data-stu-id="49bef-110">If the creation of the applications is scripted, then the packages can be automatically built using an automated process on a build server.</span></span>  
  
 <span data-ttu-id="49bef-111">请参阅以下主题有关脚本 BizTalk 应用程序部署的详细信息：</span><span class="sxs-lookup"><span data-stu-id="49bef-111">See the following topics for more information about scripting BizTalk application deployments:</span></span>  
  
-   <span data-ttu-id="49bef-112">[部署和管理 BizTalk 应用程序](http://go.microsoft.com/fwlink/?LinkId=154210)(http://go.microsoft.com/fwlink/?LinkId=154210)</span><span class="sxs-lookup"><span data-stu-id="49bef-112">[Deploying and Managing BizTalk Applications](http://go.microsoft.com/fwlink/?LinkId=154210) (http://go.microsoft.com/fwlink/?LinkId=154210)</span></span>  
  
-   <span data-ttu-id="49bef-113">[了解 BizTalk Server 应用程序部署](http://go.microsoft.com/fwlink/?LinkId=101599)(http://go.microsoft.com/fwlink/?LinkId=101599)</span><span class="sxs-lookup"><span data-stu-id="49bef-113">[Understanding BizTalk Server Application Deployment](http://go.microsoft.com/fwlink/?LinkId=101599) (http://go.microsoft.com/fwlink/?LinkId=101599)</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="49bef-114">后一种本文也适用于[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="49bef-114">This latter article also applies to [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49bef-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="49bef-115">See Also</span></span>  
 [<span data-ttu-id="49bef-116">清单： 配置 BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="49bef-116">Checklist: Configuring BizTalk Server</span></span>](../technical-guides/checklist-configuring-biztalk-server.md)