---
title: 使用脚本来部署应用程序 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9e683c5f-7576-4382-9952-d577cd00186c
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b5e8c4018540562f92d80f8c2529deebedcc9753
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65249310"
---
# <a name="using-scripts-to-deploy-applications"></a><span data-ttu-id="d905d-102">使用脚本来部署应用程序</span><span class="sxs-lookup"><span data-stu-id="d905d-102">Using Scripts to Deploy Applications</span></span>
<span data-ttu-id="d905d-103">应使用脚本来部署 BizTalk 应用程序，在可能的情况。</span><span class="sxs-lookup"><span data-stu-id="d905d-103">You should use scripts to deploy BizTalk applications where possible.</span></span> <span data-ttu-id="d905d-104">脚本在部署过程中减少人为错误的风险。</span><span class="sxs-lookup"><span data-stu-id="d905d-104">Scripting reduces the risk of human error during the deployment process.</span></span> <span data-ttu-id="d905d-105">你应记录您的部署过程中深度。</span><span class="sxs-lookup"><span data-stu-id="d905d-105">You should also document your deployment procedures in depth.</span></span> <span data-ttu-id="d905d-106">你应记录任何内容你不编写脚本非常详细的步骤。</span><span class="sxs-lookup"><span data-stu-id="d905d-106">You should document anything that you do not script with very detailed steps.</span></span> <span data-ttu-id="d905d-107">这包括记录到外部系统和非 Microsoft 组件部署到的任何更改。</span><span class="sxs-lookup"><span data-stu-id="d905d-107">This includes documenting any changes to external systems and to deployment of non-Microsoft components.</span></span>  
  
## <a name="using-btstask"></a><span data-ttu-id="d905d-108">使用 BTSTask</span><span class="sxs-lookup"><span data-stu-id="d905d-108">Using BTSTask</span></span>  
 <span data-ttu-id="d905d-109">可以使用 BTSTask.exe 编写脚本的 BizTalk 应用程序，以及导入现有创建[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].msi 程序包。</span><span class="sxs-lookup"><span data-stu-id="d905d-109">You can use BTSTask.exe to script the creation of BizTalk applications, as well as to import existing [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] .msi packages.</span></span> <span data-ttu-id="d905d-110">如果创建的应用程序编写的脚本，然后包可以自动生成的生成服务器上使用自动化的过程。</span><span class="sxs-lookup"><span data-stu-id="d905d-110">If the creation of the applications is scripted, then the packages can be automatically built using an automated process on a build server.</span></span>  
  
 <span data-ttu-id="d905d-111">请参阅有关 BizTalk 应用程序部署编写脚本的详细信息的以下主题：</span><span class="sxs-lookup"><span data-stu-id="d905d-111">See the following topics for more information about scripting BizTalk application deployments:</span></span>  
  
-   <span data-ttu-id="d905d-112">[部署和管理 BizTalk 应用程序](http://go.microsoft.com/fwlink/?LinkId=154210)(http://go.microsoft.com/fwlink/?LinkId=154210)</span><span class="sxs-lookup"><span data-stu-id="d905d-112">[Deploying and Managing BizTalk Applications](http://go.microsoft.com/fwlink/?LinkId=154210) (http://go.microsoft.com/fwlink/?LinkId=154210)</span></span>  
  
-   <span data-ttu-id="d905d-113">[了解 BizTalk Server 应用程序部署](http://go.microsoft.com/fwlink/?LinkId=101599)(http://go.microsoft.com/fwlink/?LinkId=101599)</span><span class="sxs-lookup"><span data-stu-id="d905d-113">[Understanding BizTalk Server Application Deployment](http://go.microsoft.com/fwlink/?LinkId=101599) (http://go.microsoft.com/fwlink/?LinkId=101599)</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="d905d-114">后一种本文也适用于 BizTalk Server。</span><span class="sxs-lookup"><span data-stu-id="d905d-114">This latter article also applies to BizTalk Server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d905d-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="d905d-115">See Also</span></span>  
 [<span data-ttu-id="d905d-116">清单：配置 BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="d905d-116">Checklist: Configuring BizTalk Server</span></span>](../technical-guides/checklist-configuring-biztalk-server.md)