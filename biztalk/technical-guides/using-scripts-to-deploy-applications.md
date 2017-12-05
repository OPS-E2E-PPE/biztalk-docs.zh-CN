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
ms.openlocfilehash: 9bc96c3b591baf81806182b6c3e988a46dd208ba
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
---
# <a name="using-scripts-to-deploy-applications"></a><span data-ttu-id="c597e-102">使用脚本来部署应用程序</span><span class="sxs-lookup"><span data-stu-id="c597e-102">Using Scripts to Deploy Applications</span></span>
<span data-ttu-id="c597e-103">您应使用脚本来部署 BizTalk 应用程序，在可能的情况。</span><span class="sxs-lookup"><span data-stu-id="c597e-103">You should use scripts to deploy BizTalk applications where possible.</span></span> <span data-ttu-id="c597e-104">脚本在部署过程中减少人为错误的风险。</span><span class="sxs-lookup"><span data-stu-id="c597e-104">Scripting reduces the risk of human error during the deployment process.</span></span> <span data-ttu-id="c597e-105">你应记录中深度你部署过程。</span><span class="sxs-lookup"><span data-stu-id="c597e-105">You should also document your deployment procedures in depth.</span></span> <span data-ttu-id="c597e-106">你应该记录你不具有非常详细步骤编写脚本的任何内容。</span><span class="sxs-lookup"><span data-stu-id="c597e-106">You should document anything that you do not script with very detailed steps.</span></span> <span data-ttu-id="c597e-107">这包括记录对外部系统和非 Microsoft 组件部署任何更改。</span><span class="sxs-lookup"><span data-stu-id="c597e-107">This includes documenting any changes to external systems and to deployment of non-Microsoft components.</span></span>  
  
## <a name="using-btstask"></a><span data-ttu-id="c597e-108">使用 BTSTask</span><span class="sxs-lookup"><span data-stu-id="c597e-108">Using BTSTask</span></span>  
 <span data-ttu-id="c597e-109">你可以使用 BTSTask.exe 编写脚本的 BizTalk 应用程序，以及有关导入现有创建[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].msi 包。</span><span class="sxs-lookup"><span data-stu-id="c597e-109">You can use BTSTask.exe to script the creation of BizTalk applications, as well as to import existing [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] .msi packages.</span></span> <span data-ttu-id="c597e-110">如果应用程序的创建已编写脚本，然后包可以自动生成的生成服务器上使用一个自动化的过程。</span><span class="sxs-lookup"><span data-stu-id="c597e-110">If the creation of the applications is scripted, then the packages can be automatically built using an automated process on a build server.</span></span>  
  
 <span data-ttu-id="c597e-111">请参阅以下主题有关脚本 BizTalk 应用程序部署的详细信息：</span><span class="sxs-lookup"><span data-stu-id="c597e-111">See the following topics for more information about scripting BizTalk application deployments:</span></span>  
  
-   <span data-ttu-id="c597e-112">[部署和管理 BizTalk 应用程序](http://go.microsoft.com/fwlink/?LinkId=154210)(http://go.microsoft.com/fwlink/?LinkId=154210)</span><span class="sxs-lookup"><span data-stu-id="c597e-112">[Deploying and Managing BizTalk Applications](http://go.microsoft.com/fwlink/?LinkId=154210) (http://go.microsoft.com/fwlink/?LinkId=154210)</span></span>  
  
-   <span data-ttu-id="c597e-113">[了解 BizTalk Server 应用程序部署](http://go.microsoft.com/fwlink/?LinkId=101599)(http://go.microsoft.com/fwlink/?LinkId=101599)</span><span class="sxs-lookup"><span data-stu-id="c597e-113">[Understanding BizTalk Server Application Deployment](http://go.microsoft.com/fwlink/?LinkId=101599) (http://go.microsoft.com/fwlink/?LinkId=101599)</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="c597e-114">后一种本文也适用于 BizTalk Server。</span><span class="sxs-lookup"><span data-stu-id="c597e-114">This latter article also applies to BizTalk Server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c597e-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c597e-115">See Also</span></span>  
 [<span data-ttu-id="c597e-116">清单：配置 BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="c597e-116">Checklist: Configuring BizTalk Server</span></span>](../technical-guides/checklist-configuring-biztalk-server.md)