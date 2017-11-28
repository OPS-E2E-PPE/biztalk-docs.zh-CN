---
title: "导入监视管理包 BizTalk Server 2013 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bee2bfe9-4eb0-46d4-8eee-75182202080c
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3c6dff55cce17d9b9159a8eca754f91373621929
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="import-the-biztalk-server-2013-monitoring-management-pack"></a><span data-ttu-id="9e5c8-102">导入监视管理包 BizTalk Server 2013</span><span class="sxs-lookup"><span data-stu-id="9e5c8-102">Import the BizTalk Server 2013 Monitoring Management Pack</span></span>
<span data-ttu-id="9e5c8-103">有关说明有关如何导入管理包，请参阅如何导入管理包中[Operations Manager 2007 R2/2012年](http://go.microsoft.com/fwlink/?LinkId=142351)(http://go.microsoft.com/fwlink/?LinkId=142351)。</span><span class="sxs-lookup"><span data-stu-id="9e5c8-103">For instructions about how to import a management pack, see How to Import a Management Pack in [Operations Manager 2007 R2/2012](http://go.microsoft.com/fwlink/?LinkId=142351) (http://go.microsoft.com/fwlink/?LinkId=142351).</span></span> <span data-ttu-id="9e5c8-104">后[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]导入管理包，请按照这些过程操作以完成初始配置：</span><span class="sxs-lookup"><span data-stu-id="9e5c8-104">After the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Management Pack is imported, follow these procedures to finish your initial configuration:</span></span>  
  
### <a name="to-configure-the-management-pack"></a><span data-ttu-id="9e5c8-105">若要配置管理包</span><span class="sxs-lookup"><span data-stu-id="9e5c8-105">To configure the management pack</span></span>  
  
1.  <span data-ttu-id="9e5c8-106">创建新的管理包在其中存储替代和其他自定义。</span><span class="sxs-lookup"><span data-stu-id="9e5c8-106">Create a new management pack in which you store overrides and other customizations.</span></span>  
  
2.  <span data-ttu-id="9e5c8-107">若要启用代理程序设置，请按照下列步骤：</span><span class="sxs-lookup"><span data-stu-id="9e5c8-107">To enable the Agent Proxy setting, follow these steps:</span></span>  
  
    1.  <span data-ttu-id="9e5c8-108">打开操作控制台，然后单击管理按钮。</span><span class="sxs-lookup"><span data-stu-id="9e5c8-108">Open the Operations console and then click the Administration button.</span></span>  
  
    2.  <span data-ttu-id="9e5c8-109">在管理员窗格中，单击**代理管理**。</span><span class="sxs-lookup"><span data-stu-id="9e5c8-109">In the Administrator pane, click **Agent Managed**.</span></span>  
  
    3.  <span data-ttu-id="9e5c8-110">双击列表中的代理。</span><span class="sxs-lookup"><span data-stu-id="9e5c8-110">Double-click an agent in the list.</span></span>  
  
    4.  <span data-ttu-id="9e5c8-111">在安全选项卡，选择**允许此代理充当代理并发现其他计算机上的托管的对象**。</span><span class="sxs-lookup"><span data-stu-id="9e5c8-111">On the Security tab, select **Allow this agent to act as a proxy and discover managed objects on other computers**.</span></span>  
  
    5.  <span data-ttu-id="9e5c8-112">为每个 BizTalk 服务器安装的代理重复步骤 3-4。</span><span class="sxs-lookup"><span data-stu-id="9e5c8-112">Repeat steps 3 through 4 for each agent that is installed on a BizTalk Server.</span></span>