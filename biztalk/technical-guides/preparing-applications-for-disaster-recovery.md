---
title: 准备应用程序的灾难恢复 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0ef93099-aa6b-424a-a4ce-87d855c6afe3
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7028b1386f71f653dfc41b9de2522cdbd8d02126
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22302333"
---
# <a name="preparing-applications-for-disaster-recovery"></a><span data-ttu-id="5d69b-102">准备应用程序的灾难恢复</span><span class="sxs-lookup"><span data-stu-id="5d69b-102">Preparing Applications for Disaster Recovery</span></span>
<span data-ttu-id="5d69b-103">在组还原在灾难恢复站点时，BizTalk 应用程序 （二进制文件和配置项目如接收位置和发送端口） 将部署到生产 BizTalk 组。</span><span class="sxs-lookup"><span data-stu-id="5d69b-103">BizTalk applications (binaries and configuration artifacts such as receive locations and send ports) are deployed to the production BizTalk group when the group is restored at the disaster recovery site.</span></span> <span data-ttu-id="5d69b-104">此配置可能需要更改取决于是否有配置位置，例如接收位置和发送生产特定的端口。</span><span class="sxs-lookup"><span data-stu-id="5d69b-104">This configuration may have to be altered depending on whether there are configuration locations such as receive locations and send ports that are production-specific.</span></span>  
  
 <span data-ttu-id="5d69b-105">若要在灾难恢复站点上，加快应用程序还原[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]安装二进制文件的.msi 文件[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]运行时服务器必须保持最新的灾难恢复[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]运行时服务器。</span><span class="sxs-lookup"><span data-stu-id="5d69b-105">To speed the restoration of applications at the disaster recovery site, a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] .msi file that installs the binaries on the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] run-time servers must be kept up-to-date on the disaster recovery [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] run-time servers.</span></span> <span data-ttu-id="5d69b-106">灾难恢复特定应用程序配置.msi 文件在灾难恢复站点还原生产 BizTalk 组时，可能需要安装才能配置，灾难特定于恢复的项目的应用程序，例如接收位置并根据需要发送端口。</span><span class="sxs-lookup"><span data-stu-id="5d69b-106">When the production BizTalk group is restored at the disaster recovery site, a disaster recovery-specific application configuration .msi file may need to be installed in order to configure the application for disaster recovery-specific artifacts, such as receive locations and send ports, as necessary.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d69b-107">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5d69b-107">See Also</span></span>  
 [<span data-ttu-id="5d69b-108">部署应用程序</span><span class="sxs-lookup"><span data-stu-id="5d69b-108">Deploying an Application</span></span>](../technical-guides/deploying-an-application.md)