---
title: 安装和配置 BizTalk Server 消息传送的服务器上 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BizTalk Server, installing on BizTalk Messaging servers
- BizTalk Server, configuring
- BizTalk Messaging servers, configuring BizTalk Server
- BizTalk Messaging servers, installing BizTalk Server
ms.assetid: 8aaa1b97-90f0-4317-9403-ac8b5b9f80e3
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b5f4013c1fe315646ea7a2ff34772169a03a2d66
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36989566"
---
# <a name="installing-and-configuring-biztalk-server-on-the-messaging-server"></a><span data-ttu-id="b479c-102">安装和配置 BizTalk Server 消息传送的服务器上</span><span class="sxs-lookup"><span data-stu-id="b479c-102">Installing and Configuring BizTalk Server on the Messaging Server</span></span>
<span data-ttu-id="b479c-103">本部分介绍如何安装和配置 BizTalk Server 以便用作消息传送服务器用于连接到 SWIFT 网络。</span><span class="sxs-lookup"><span data-stu-id="b479c-103">This section describes how to install and configure BizTalk Server to be used as the messaging server for connecting to the SWIFT network.</span></span>  

### <a name="to-install-and-configure-biztalk-server-on-the-messaging-server"></a><span data-ttu-id="b479c-104">若要安装和配置 BizTalk Server 消息传送服务器上</span><span class="sxs-lookup"><span data-stu-id="b479c-104">To install and configure BizTalk Server on the Messaging Server</span></span>  

1. <span data-ttu-id="b479c-105">执行的自定义安装[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]选择除 EDI、 工作流服务 (HWS) 和 MRSR 站点之外的所有功能，除非所需的其他应用程序。</span><span class="sxs-lookup"><span data-stu-id="b479c-105">Perform a custom installation of [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] choosing all the features except EDI, Human Workflow Services (HWS), and MRSR site, unless required by other applications.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="b479c-106">请注意，在单台计算机部署中，此计算机是作为一个运行 HTTP 前端服务在同一台计算机。</span><span class="sxs-lookup"><span data-stu-id="b479c-106">Note that in single-computer deployment, this computer is the same computer as the one that runs the HTTP front-end service.</span></span>  

2. <span data-ttu-id="b479c-107">执行的配置[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="b479c-107">Perform configuration of [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="b479c-108">不安装消息队列，因为我们将安装[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]称为 MSMQT 的 MSMQ 版本。</span><span class="sxs-lookup"><span data-stu-id="b479c-108">Do not install Message Queuing, because we will be installing the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] version of MSMQ known as MSMQT.</span></span> <span data-ttu-id="b479c-109">有关 MSMQT 的详细信息，请参阅 BizTalk 消息队列适配器 (MSMQT) 配置 MSDN Web 站点上[ http://go.microsoft.com/fwlink/?LinkID=48875 ](http://go.microsoft.com/fwlink/?LinkID=48875)。</span><span class="sxs-lookup"><span data-stu-id="b479c-109">For more information about MSMQT, see BizTalk Message Queuing Adapter (MSMQT) Configuration on the MSDN Web site at [http://go.microsoft.com/fwlink/?LinkID=48875](http://go.microsoft.com/fwlink/?LinkID=48875).</span></span>  

3. <span data-ttu-id="b479c-110">安装所需的任何其他修补程序[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]安装指南中为可用。</span><span class="sxs-lookup"><span data-stu-id="b479c-110">Install any additional hotfixes required by [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)] as available in the installation guide.</span></span> <span data-ttu-id="b479c-111">在此发布时，没有所需的修补程序。</span><span class="sxs-lookup"><span data-stu-id="b479c-111">At the time of this publication, there are no required hotfixes.</span></span>
