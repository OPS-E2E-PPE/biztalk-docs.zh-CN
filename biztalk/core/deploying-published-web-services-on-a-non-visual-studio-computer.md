---
title: 部署发布非 Visual Studio 计算机上的 Web 服务 |Microsoft 文档
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
ms.openlocfilehash: ad894c257bdd2eed6462b63c0e921f78ca13c17e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22239029"
---
# <a name="deploying-published-web-services-on-a-non-visual-studio-computer"></a><span data-ttu-id="10929-102">在无 Visual Studio 的计算机上部署已发布 Web Services</span><span class="sxs-lookup"><span data-stu-id="10929-102">Deploying Published Web Services on a Non-Visual Studio Computer</span></span>
<span data-ttu-id="10929-103">若要部署你已发布的 Web 服务没有的计算机上[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]安装，你需要创建的 Web 安装程序项目，分发的 Web 安装程序包 （.msi 文件），请将软件包安装在非[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]计算机，并配置已安装Web 服务。</span><span class="sxs-lookup"><span data-stu-id="10929-103">To deploy your published Web service on a computer that does not have [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] installed, you need to create a Web setup project, distribute the Web setup package (.msi file), install the package on the non-[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] computer, and configure the installed Web service.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="10929-104">还可以使用 BizTalk Server 管理控制台创建 MSI 文件，该文件中打包了包含已发布 Web Services 项目的 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="10929-104">You can also use BizTalk Server Administration Console to create MSI files packaging BizTalk Applications containing the published Web service projects.</span></span> <span data-ttu-id="10929-105">此 MSI 文件可用于在无 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 的计算机上部署 Web 服务项目。</span><span class="sxs-lookup"><span data-stu-id="10929-105">This MSI files can be used to deploy the Web service projects on a Non [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Computer.</span></span> <span data-ttu-id="10929-106">有关如何创建使用 BizTalk Server 管理控制台的 MSI 文件的详细信息，请参阅[how to Export BizTalk 应用程序如何](../core/how-to-export-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="10929-106">For more information about how to create MSI files using BizTalk Server Administration console, see [How to Export a BizTalk Application](../core/how-to-export-a-biztalk-application.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="10929-107">本节内容</span><span class="sxs-lookup"><span data-stu-id="10929-107">In This Section</span></span>  
  
-   [<span data-ttu-id="10929-108">如何为你的已发布的 Web 服务中创建 Web 安装程序</span><span class="sxs-lookup"><span data-stu-id="10929-108">How to Create a Web Setup for Your Published Web Service</span></span>](../core/how-to-create-a-web-setup-for-your-published-web-service.md)  
  
-   [<span data-ttu-id="10929-109">如何将 Web 安装程序包分发</span><span class="sxs-lookup"><span data-stu-id="10929-109">How to Distribute the Web Setup Package</span></span>](../core/how-to-distribute-the-web-setup-package.md)  
  
-   [<span data-ttu-id="10929-110">如何安装 Web 安装程序包</span><span class="sxs-lookup"><span data-stu-id="10929-110">How to Install the Web Setup Package</span></span>](../core/how-to-install-the-web-setup-package.md)  
  
-   [<span data-ttu-id="10929-111">如何配置已安装的 Web 服务</span><span class="sxs-lookup"><span data-stu-id="10929-111">How to Configure the Installed Web Service</span></span>](../core/how-to-configure-the-installed-web-service.md)  
  
## <a name="see-also"></a><span data-ttu-id="10929-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="10929-112">See Also</span></span>  
 [<span data-ttu-id="10929-113">部署 BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="10929-113">Deploying BizTalk Applications</span></span>](../core/deploying-biztalk-applications.md)