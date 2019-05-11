---
title: 部署已发布的非 Visual Studio 计算机上的 Web 服务 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Web services, publishing
- deploying, Web services
- Web services, planning
- Web services, deploying
ms.assetid: e9f8e801-21f3-4458-b05c-206b72868916
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0e7ccca1ad7e5b3d480e7075c059f11f51c28738
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389554"
---
# <a name="deploying-published-web-services-on-a-non-visual-studio-computer"></a><span data-ttu-id="3a88f-102">在无 Visual Studio 的计算机上部署已发布 Web Services</span><span class="sxs-lookup"><span data-stu-id="3a88f-102">Deploying Published Web Services on a Non-Visual Studio Computer</span></span>
<span data-ttu-id="3a88f-103">若要将已发布的 Web 服务没有在计算机上部署[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]安装，需要创建 Web 安装项目、 分发 Web 安装包 （.msi 文件）、 将软件包安装在非[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]计算机，并配置已安装Web 服务。</span><span class="sxs-lookup"><span data-stu-id="3a88f-103">To deploy your published Web service on a computer that does not have [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] installed, you need to create a Web setup project, distribute the Web setup package (.msi file), install the package on the non-[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] computer, and configure the installed Web service.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3a88f-104">此外可以使用 BizTalk Server 管理控制台创建 MSI 文件打包 BizTalk 应用程序包含已发布的 Web 服务项目。</span><span class="sxs-lookup"><span data-stu-id="3a88f-104">You can also use BizTalk Server Administration Console to create MSI files packaging BizTalk Applications containing the published Web service projects.</span></span> <span data-ttu-id="3a88f-105">此 MSI 文件可用于部署 Web 服务项目上非[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]计算机。</span><span class="sxs-lookup"><span data-stu-id="3a88f-105">This MSI files can be used to deploy the Web service projects on a Non [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Computer.</span></span> <span data-ttu-id="3a88f-106">有关如何使用 BizTalk Server 管理控制台创建 MSI 文件的详细信息，请参阅[如何导出 BizTalk 应用程序](../core/how-to-export-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="3a88f-106">For more information about how to create MSI files using BizTalk Server Administration console, see [How to Export a BizTalk Application](../core/how-to-export-a-biztalk-application.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="3a88f-107">本节内容</span><span class="sxs-lookup"><span data-stu-id="3a88f-107">In This Section</span></span>  
  
-   [<span data-ttu-id="3a88f-108">如何为已发布的 Web 服务创建 Web 安装程序</span><span class="sxs-lookup"><span data-stu-id="3a88f-108">How to Create a Web Setup for Your Published Web Service</span></span>](../core/how-to-create-a-web-setup-for-your-published-web-service.md)  
  
-   [<span data-ttu-id="3a88f-109">如何分发 Web 安装包</span><span class="sxs-lookup"><span data-stu-id="3a88f-109">How to Distribute the Web Setup Package</span></span>](../core/how-to-distribute-the-web-setup-package.md)  
  
-   [<span data-ttu-id="3a88f-110">如何安装 Web 安装包</span><span class="sxs-lookup"><span data-stu-id="3a88f-110">How to Install the Web Setup Package</span></span>](../core/how-to-install-the-web-setup-package.md)  
  
-   [<span data-ttu-id="3a88f-111">如何配置已安装的 Web 服务</span><span class="sxs-lookup"><span data-stu-id="3a88f-111">How to Configure the Installed Web Service</span></span>](../core/how-to-configure-the-installed-web-service.md)  
  
## <a name="see-also"></a><span data-ttu-id="3a88f-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="3a88f-112">See Also</span></span>  
 [<span data-ttu-id="3a88f-113">部署 BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="3a88f-113">Deploying BizTalk Applications</span></span>](../core/deploying-biztalk-applications.md)