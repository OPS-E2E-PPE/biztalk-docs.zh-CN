---
title: 准备灾难恢复 BizTalk 服务器 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 14c2c25d-30c5-4e90-a744-f084befa2c1d
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9379136f0845c7c4c987170747a28bd3c50206c4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22302141"
---
# <a name="preparing-the-disaster-recovery-biztalk-servers"></a><span data-ttu-id="b7c41-102">准备灾难恢复 BizTalk 服务器</span><span class="sxs-lookup"><span data-stu-id="b7c41-102">Preparing the Disaster Recovery BizTalk Servers</span></span>
<span data-ttu-id="b7c41-103">安装[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]在灾难恢复站点按照中的建议的运行时服务器[BizTalk Server 2010 安装和升级指南](http://go.microsoft.com/fwlink/?LinkID=194815)(http://go.microsoft.com/fwlink/?LinkID=194815)。</span><span class="sxs-lookup"><span data-stu-id="b7c41-103">Install [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] run-time servers at the disaster recovery site following the recommendations in [BizTalk Server 2010 Installation and Upgrade Guides](http://go.microsoft.com/fwlink/?LinkID=194815) (http://go.microsoft.com/fwlink/?LinkID=194815).</span></span> <span data-ttu-id="b7c41-104">配置这些[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]使用 BizTalk 配置向导以将它们加入到生产 BizTalk 组的运行时服务器。</span><span class="sxs-lookup"><span data-stu-id="b7c41-104">Configure these [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] run-time servers using the BizTalk Configuration Wizard to join them to the production BizTalk group.</span></span> <span data-ttu-id="b7c41-105">配置时[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]在灾难恢复站点 （包括灾难恢复企业单一登录在主密钥服务器） 的运行时服务器，请确保为：</span><span class="sxs-lookup"><span data-stu-id="b7c41-105">When configuring the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] run-time servers at the disaster recovery site (including the disaster recovery Enterprise Single Sign-On Master Secret server) make sure to:</span></span>  
  
-   <span data-ttu-id="b7c41-106">选择**否**问题"这是主密钥服务器？"</span><span class="sxs-lookup"><span data-stu-id="b7c41-106">Select **No** to the question “Is this the master secret server?”</span></span>  
  
-   <span data-ttu-id="b7c41-107">选择**联接**问题"是否要创建或加入 BizTalk Server 组？"</span><span class="sxs-lookup"><span data-stu-id="b7c41-107">Select **Join** to the question “Do you want to create or join a BizTalk Server group?”</span></span>  
  
 <span data-ttu-id="b7c41-108">配置后[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]运行时灾难恢复服务器，请在对应于生产站点主机实例，但不是会开始这些主机实例的灾难恢复站点上创建 BizTalk 主机实例。</span><span class="sxs-lookup"><span data-stu-id="b7c41-108">After configuring the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] run-time disaster recovery servers, create BizTalk host instances on the disaster recovery site that correspond to the production site host instances, but do not start these host instances.</span></span> <span data-ttu-id="b7c41-109">例如，如果生产站点具有三个主机**发送**，**接收**，和**Orchestration**上 server1 和 server2，服务器 3 的实例，创建三个对应DRserver1，DRserver2，DRserver3 上的主机实例。</span><span class="sxs-lookup"><span data-stu-id="b7c41-109">For example, if the production site has three Hosts **Send**, **Receive**, and **Orchestration** with instances on server1, server2, and server3, create three corresponding host instances on DRserver1, DRserver2, DRserver3.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b7c41-110">所有[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]的相关 Windows 服务，如 BizTalk 主机实例和在灾难恢复站点的规则引擎服务应设置为"已禁用"在服务管理器以防止灾难恢复站点执行任何处理。</span><span class="sxs-lookup"><span data-stu-id="b7c41-110">All [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]-related Windows services such as the BizTalk Host Instance and Rules Engine Service at the disaster recovery site should be set to “disabled” in the Services Manager to prevent the disaster recovery site from performing any processing.</span></span>  
  
 <span data-ttu-id="b7c41-111">你可以安装和配置不同数量的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]在灾难恢复站点不是在生产中运行的运行时服务器。</span><span class="sxs-lookup"><span data-stu-id="b7c41-111">You can install and configure a different number of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] run-time servers in the disaster recovery site than are running in production.</span></span> <span data-ttu-id="b7c41-112">但是，采用这种方法，以避免重载灾难恢复站点中的服务器，如果发生灾难恢复事件时要格外小心。</span><span class="sxs-lookup"><span data-stu-id="b7c41-112">Use caution when taking this approach however, so as to avoid overloading the servers in the disaster recovery site if a disaster recovery event occurs.</span></span> <span data-ttu-id="b7c41-113">一旦完全还原 BizTalk 组所表示的组的数据库，并且所有所需的系统更改执行 BizTalk 组，可以运行脚本以加入[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]到 BizTalk 组的运行时服务器。</span><span class="sxs-lookup"><span data-stu-id="b7c41-113">Once the BizTalk group as represented by the set of databases is fully restored, and all required system changes are performed for the BizTalk group, scripts can be run to join the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] run-time servers to the BizTalk group.</span></span>