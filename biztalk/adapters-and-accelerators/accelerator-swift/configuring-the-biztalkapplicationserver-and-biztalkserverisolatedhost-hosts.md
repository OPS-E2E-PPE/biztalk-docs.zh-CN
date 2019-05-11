---
title: 配置 BizTalkApplicationServer 和 BizTalkServerIsolatedHost 主机 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- configuring, hosts
- BizTalkApplicationServer host
- hosts
- BizTalkServerIsolatedHost host
ms.assetid: 17bc9f01-ff87-427d-8411-6a065814ba1e
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 462abf2b0b7f9fc0df8a1b754d0fa5803656ab88
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65378532"
---
# <a name="configuring-the-biztalkapplicationserver-and-biztalkserverisolatedhost-hosts"></a><span data-ttu-id="ecf77-102">配置 BizTalkApplicationServer 和 BizTalkServerIsolatedHost 主机</span><span class="sxs-lookup"><span data-stu-id="ecf77-102">Configuring the BizTalkApplicationServer and BizTalkServerIsolatedHost Hosts</span></span>
<span data-ttu-id="ecf77-103">若要限制到 BizTalk 消息传送服务器的消息 （发送和接收消息），需要配置的默认主机，哪些运行 MSMQT 发送并接收处理程序，仅在消息传送的服务器上运行。</span><span class="sxs-lookup"><span data-stu-id="ecf77-103">To limit the messaging (sending and receiving messages) to the BizTalk Messaging servers, you need to configure the default hosts, which are running the MSMQT send and receive handlers, to run only on the messaging servers.</span></span>  
  
### <a name="to-configure-the-default-hosts"></a><span data-ttu-id="ecf77-104">若要配置的默认主机</span><span class="sxs-lookup"><span data-stu-id="ecf77-104">To configure the default hosts</span></span>  
  
1.  <span data-ttu-id="ecf77-105">使用 BizTalk 管理控制台，从 BizTalkApplicationServer 主机中删除业务流程服务器主机实例：</span><span class="sxs-lookup"><span data-stu-id="ecf77-105">Using the BizTalk Administration Console, delete the orchestration servers host instances from the BizTalkApplicationServer host:</span></span>  
  
    -   <span data-ttu-id="ecf77-106">右键单击每个主机实例，然后单击**停止**。</span><span class="sxs-lookup"><span data-stu-id="ecf77-106">Right-click each host instance and click **Stop**.</span></span>  
  
    -   <span data-ttu-id="ecf77-107">右键单击每个主机实例，然后单击**删除**。</span><span class="sxs-lookup"><span data-stu-id="ecf77-107">Right-click each host instance and click **Delete**.</span></span>  
  
2.  <span data-ttu-id="ecf77-108">使用 BizTalk 管理控制台，从 BizTalkServerIsolatedHost 主机中删除业务流程服务器主机实例：</span><span class="sxs-lookup"><span data-stu-id="ecf77-108">Using the BizTalk Administration Console, delete the orchestration servers host instances from the BizTalkServerIsolatedHost host:</span></span>  
  
    -   <span data-ttu-id="ecf77-109">右键单击每个主机实例，然后单击删除。</span><span class="sxs-lookup"><span data-stu-id="ecf77-109">Right-click each host instance and click Delete.</span></span>  
  
3.  <span data-ttu-id="ecf77-110">配置主机后，重新启动所有服务器上的所有主机实例。</span><span class="sxs-lookup"><span data-stu-id="ecf77-110">After you have configured the hosts, restart all the host instances on all the servers.</span></span>