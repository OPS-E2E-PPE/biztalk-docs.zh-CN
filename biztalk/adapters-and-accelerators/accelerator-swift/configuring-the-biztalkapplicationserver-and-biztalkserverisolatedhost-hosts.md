---
title: "配置 BizTalkApplicationServer 和 BizTalkServerIsolatedHost 主机 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- configuring, hosts
- BizTalkApplicationServer host
- hosts
- BizTalkServerIsolatedHost host
ms.assetid: 17bc9f01-ff87-427d-8411-6a065814ba1e
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8459debcd52ce990bc98adf3a2a2372206bae336
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-the-biztalkapplicationserver-and-biztalkserverisolatedhost-hosts"></a><span data-ttu-id="d87e2-102">配置 BizTalkApplicationServer 和 BizTalkServerIsolatedHost 主机</span><span class="sxs-lookup"><span data-stu-id="d87e2-102">Configuring the BizTalkApplicationServer and BizTalkServerIsolatedHost Hosts</span></span>
<span data-ttu-id="d87e2-103">若要限制到 BizTalk 消息传送服务器的消息传送的 （发送和接收消息），你需要配置运行 MSMQT 发送和接收处理程序，仅在消息传递的服务器上运行的默认主机。</span><span class="sxs-lookup"><span data-stu-id="d87e2-103">To limit the messaging (sending and receiving messages) to the BizTalk Messaging servers, you need to configure the default hosts, which are running the MSMQT send and receive handlers, to run only on the messaging servers.</span></span>  
  
### <a name="to-configure-the-default-hosts"></a><span data-ttu-id="d87e2-104">若要将默认主机配置</span><span class="sxs-lookup"><span data-stu-id="d87e2-104">To configure the default hosts</span></span>  
  
1.  <span data-ttu-id="d87e2-105">使用 BizTalk 管理控制台，从 BizTalkApplicationServer 主机中删除业务流程服务器主机实例：</span><span class="sxs-lookup"><span data-stu-id="d87e2-105">Using the BizTalk Administration Console, delete the orchestration servers host instances from the BizTalkApplicationServer host:</span></span>  
  
    -   <span data-ttu-id="d87e2-106">右键单击每个主机实例，然后单击**停止**。</span><span class="sxs-lookup"><span data-stu-id="d87e2-106">Right-click each host instance and click **Stop**.</span></span>  
  
    -   <span data-ttu-id="d87e2-107">右键单击每个主机实例，然后单击**删除**。</span><span class="sxs-lookup"><span data-stu-id="d87e2-107">Right-click each host instance and click **Delete**.</span></span>  
  
2.  <span data-ttu-id="d87e2-108">使用 BizTalk 管理控制台，从 BizTalkServerIsolatedHost 主机中删除业务流程服务器主机实例：</span><span class="sxs-lookup"><span data-stu-id="d87e2-108">Using the BizTalk Administration Console, delete the orchestration servers host instances from the BizTalkServerIsolatedHost host:</span></span>  
  
    -   <span data-ttu-id="d87e2-109">右键单击每个主机实例，然后单击删除。</span><span class="sxs-lookup"><span data-stu-id="d87e2-109">Right-click each host instance and click Delete.</span></span>  
  
3.  <span data-ttu-id="d87e2-110">配置主机后，重新启动所有服务器上的所有主机实例。</span><span class="sxs-lookup"><span data-stu-id="d87e2-110">After you have configured the hosts, restart all the host instances on all the servers.</span></span>