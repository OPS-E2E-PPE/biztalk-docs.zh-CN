---
title: 如何还原应用程序和启用处理 |Microsoft Docs
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
ms.openlocfilehash: d4c73d3ac6d96b1cfae4a8e8092669b6b0edcad0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65400298"
---
# <a name="how-to-restore-applications-and-enable-processing"></a><span data-ttu-id="fe91d-102">如何还原应用程序和启用处理</span><span class="sxs-lookup"><span data-stu-id="fe91d-102">How to Restore Applications and Enable Processing</span></span>
<span data-ttu-id="fe91d-103">在 BizTalk 组中配置的应用程序并启用主题所述的步骤操作后的应用程序处理[如何更新运行时计算机](../technical-guides/how-to-update-the-runtime-computers.md)。</span><span class="sxs-lookup"><span data-stu-id="fe91d-103">Configure the applications in the BizTalk group and enable application processing after following the steps described in the topic [How to Update the Runtime Computers](../technical-guides/how-to-update-the-runtime-computers.md).</span></span>  
  
### <a name="to-enable-application-configuration-and-restore-application-processing"></a><span data-ttu-id="fe91d-104">若要启用应用程序配置和还原应用程序处理</span><span class="sxs-lookup"><span data-stu-id="fe91d-104">To enable application configuration and restore application processing</span></span>  
  
1. <span data-ttu-id="fe91d-105">运行[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]组中每个 BizTalk 服务器上的应用程序安装 MSI 文件。</span><span class="sxs-lookup"><span data-stu-id="fe91d-105">Run the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Application Installation MSI file on each BizTalk server in the group.</span></span>  
  
2. <span data-ttu-id="fe91d-106">运行[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]组来配置应用程序的灾难恢复站点中的一台服务器上的应用程序配置 MSI 文件。</span><span class="sxs-lookup"><span data-stu-id="fe91d-106">Run the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Application Configuration MSI file on one server in the group to configure the application for the disaster recovery site.</span></span> <span data-ttu-id="fe91d-107">名称为接收位置和发送端口将保持不变。</span><span class="sxs-lookup"><span data-stu-id="fe91d-107">The names for receive locations and send ports remain the same.</span></span> <span data-ttu-id="fe91d-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]应用程序配置 MSI 文件将更新绑定，以便这些项目指向灾难恢复环境中的正确位置。</span><span class="sxs-lookup"><span data-stu-id="fe91d-108">The [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Application Configuration MSI file updates bindings so that these artifacts point to the correct locations in the disaster recovery environment.</span></span>  
  
   > [!NOTE]  
   >  <span data-ttu-id="fe91d-109">如果接收位置和发送端口不会受到影响的生产站点丢失，可能不需要重新配置灾难恢复特定于位置的应用程序。</span><span class="sxs-lookup"><span data-stu-id="fe91d-109">If receive locations and send ports are not affected by the loss of the production site, it may not be necessary to reconfigure the application with disaster recovery-specific locations.</span></span>  
  
3. <span data-ttu-id="fe91d-110">还原应用程序处理所有的应用程序，从而接收位置、 发送端口和主机实例。</span><span class="sxs-lookup"><span data-stu-id="fe91d-110">Restore application processing by enabling all application receive locations, send ports, and host instances.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe91d-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="fe91d-111">See Also</span></span>  
 [<span data-ttu-id="fe91d-112">恢复运行时计算机</span><span class="sxs-lookup"><span data-stu-id="fe91d-112">Recovering the Runtime Computers</span></span>](../technical-guides/recovering-the-runtime-computers.md)