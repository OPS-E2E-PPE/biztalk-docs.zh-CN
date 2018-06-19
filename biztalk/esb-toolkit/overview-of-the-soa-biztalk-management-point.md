---
title: SOA BizTalk 管理点的概述 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0d4c3a30-c50e-4c1c-9f59-d9a364078388
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 60f73834a9bc02e371d4050115b1eccf5e88e02f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22294925"
---
# <a name="overview-of-the-soa-biztalk-management-point"></a><span data-ttu-id="37f9c-102">SOA BizTalk 管理点的概述</span><span class="sxs-lookup"><span data-stu-id="37f9c-102">Overview of the SOA BizTalk Management Point</span></span>
<span data-ttu-id="37f9c-103">与 SOA 服务管理器和 Workbench 产品本机集成 BizTalk 管理点。</span><span class="sxs-lookup"><span data-stu-id="37f9c-103">The BizTalk Management Point natively integrates with SOA Service Manager and Workbench products.</span></span> <span data-ttu-id="37f9c-104">不像典型 Web 服务的管理点，此实现器关联与 Microsoft BizTalk Server 环境中，按 BizTalk Server 表示由提供的服务接收位置和发送端口。</span><span class="sxs-lookup"><span data-stu-id="37f9c-104">Unlike the typical Web Services Management Point, this implementation is associated with services provided by the Microsoft BizTalk Server environment, expressed in terms of BizTalk Server receive locations and send ports.</span></span> <span data-ttu-id="37f9c-105">由于任意性质接收位置和发送端口 （配置免受各种 BizTalk Server 适配器），这些服务不一定与 Web 服务相关联，但可以将它们视为 Web 服务根据 SOA 服务管理器和 SOA Workbench。</span><span class="sxs-lookup"><span data-stu-id="37f9c-105">Because of the arbitrary nature of receive locations and send ports (configured against a variety of BizTalk Server adapters), these services are not necessarily associated with Web services, but they can be treated as Web services in terms of the SOA Service Manager and SOA Workbench.</span></span>  
  
 <span data-ttu-id="37f9c-106">图 1 显示 SOA 服务管理器 Web 应用程序显示的示例应用程序的 Workbench 页。</span><span class="sxs-lookup"><span data-stu-id="37f9c-106">Figure 1 shows the SOA Service Manager Web application displaying the Workbench page for an example application.</span></span> <span data-ttu-id="37f9c-107">左侧树视图允许用户浏览应用程序和 BizTalk Server 中安装的服务和右侧窗格中，用户可以查看应用程序详细信息、 操作、 访问端口、 类别、 规则和监视信息。</span><span class="sxs-lookup"><span data-stu-id="37f9c-107">The left-side tree view allows users to navigate through the applications and services installed within BizTalk Server, and the right-side pane allows users to view application details, operations, access ports, categories, rules, and monitoring information.</span></span>  
  
 <span data-ttu-id="37f9c-108">![Ch9 &#45;SOAServiceManager](../esb-toolkit/media/ch9-soaservicemanager.jpg "Ch9 SOAServiceManager")</span><span class="sxs-lookup"><span data-stu-id="37f9c-108">![Ch9&#45;SOAServiceManager](../esb-toolkit/media/ch9-soaservicemanager.jpg "Ch9-SOAServiceManager")</span></span>  
  
 <span data-ttu-id="37f9c-109">**图 1**</span><span class="sxs-lookup"><span data-stu-id="37f9c-109">**Figure 1**</span></span>  
  
 <span data-ttu-id="37f9c-110">**SOA 服务管理器在 Workbench 页上显示可用的监视功能**</span><span class="sxs-lookup"><span data-stu-id="37f9c-110">**The SOA Service Manager showing the monitoring features available on the Workbench page**</span></span>  
  
 <span data-ttu-id="37f9c-111">你可以监视所有应用程序 （所有发送端口和接收位置） 中的操作或特定操作;Workbench 显示了一个通过所选传递的消息列表发送端口和接收位置。</span><span class="sxs-lookup"><span data-stu-id="37f9c-111">You can monitor all the operations within an application (all send ports and receive locations), or specific operations; the Workbench shows a list of the messages passing through the selected send ports and receive locations.</span></span> <span data-ttu-id="37f9c-112">双击列表中的消息时，该 Workbench 将显示消息，并将其上下文属性的详细的信息 （如果启用了录制）。</span><span class="sxs-lookup"><span data-stu-id="37f9c-112">When you double-click a message in the list, the Workbench displays details of the message, and its context properties (if recording is enabled).</span></span> <span data-ttu-id="37f9c-113">或者，您可以选择特定的服务和监视器中实时通过该服务传递的消息。</span><span class="sxs-lookup"><span data-stu-id="37f9c-113">Alternatively, you can select a specific service and monitor in real-time messages passing through that service.</span></span>