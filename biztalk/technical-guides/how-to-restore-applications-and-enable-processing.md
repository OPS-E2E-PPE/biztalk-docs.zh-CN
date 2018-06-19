---
title: 如何还原应用程序和启用处理 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 83144965-a51a-481a-afd6-7f573b69badb
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 65ae913d45f45b13458294863714823a41ff4e44
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22297829"
---
# <a name="how-to-restore-applications-and-enable-processing"></a><span data-ttu-id="4babe-102">如何还原应用程序和启用处理</span><span class="sxs-lookup"><span data-stu-id="4babe-102">How to Restore Applications and Enable Processing</span></span>
<span data-ttu-id="4babe-103">配置 BizTalk 组中的应用程序并启用主题所述的步骤操作后的应用程序处理[如何更新运行时计算机](../technical-guides/how-to-update-the-runtime-computers.md)。</span><span class="sxs-lookup"><span data-stu-id="4babe-103">Configure the applications in the BizTalk group and enable application processing after following the steps described in the topic [How to Update the Runtime Computers](../technical-guides/how-to-update-the-runtime-computers.md).</span></span>  
  
### <a name="to-enable-application-configuration-and-restore-application-processing"></a><span data-ttu-id="4babe-104">若要启用应用程序配置和还原应用程序处理</span><span class="sxs-lookup"><span data-stu-id="4babe-104">To enable application configuration and restore application processing</span></span>  
  
1.  <span data-ttu-id="4babe-105">运行[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]组中每个 BizTalk 服务器上的应用程序安装 MSI 文件。</span><span class="sxs-lookup"><span data-stu-id="4babe-105">Run the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Application Installation MSI file on each BizTalk server in the group.</span></span>  
  
2.  <span data-ttu-id="4babe-106">运行[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]组配置应用程序的灾难恢复站点中的一台服务器上的应用程序配置 MSI 文件。</span><span class="sxs-lookup"><span data-stu-id="4babe-106">Run the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Application Configuration MSI file on one server in the group to configure the application for the disaster recovery site.</span></span> <span data-ttu-id="4babe-107">接收位置和发送端口将保持不变的名称。</span><span class="sxs-lookup"><span data-stu-id="4babe-107">The names for receive locations and send ports remain the same.</span></span> <span data-ttu-id="4babe-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]应用程序配置 MSI 文件将更新绑定，以便这些项目指向灾难恢复环境中的正确位置。</span><span class="sxs-lookup"><span data-stu-id="4babe-108">The [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Application Configuration MSI file updates bindings so that these artifacts point to the correct locations in the disaster recovery environment.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="4babe-109">如果接收位置和发送端口不受影响的丢失将生产站点的情况下，可能不需要重新配置灾难恢复特定位置的应用程序。</span><span class="sxs-lookup"><span data-stu-id="4babe-109">If receive locations and send ports are not affected by the loss of the production site, it may not be necessary to reconfigure the application with disaster recovery-specific locations.</span></span>  
  
3.  <span data-ttu-id="4babe-110">通过启用所有应用程序的还原应用程序处理接收位置、 发送端口和主机实例。</span><span class="sxs-lookup"><span data-stu-id="4babe-110">Restore application processing by enabling all application receive locations, send ports, and host instances.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4babe-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4babe-111">See Also</span></span>  
 [<span data-ttu-id="4babe-112">恢复运行时计算机</span><span class="sxs-lookup"><span data-stu-id="4babe-112">Recovering the Runtime Computers</span></span>](../technical-guides/recovering-the-runtime-computers.md)