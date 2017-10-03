---
title: "安装和消息传送的服务器上配置 BizTalk Server |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- BizTalk Server, installing on BizTalk Messaging servers
- BizTalk Server, configuring
- BizTalk Messaging servers, configuring BizTalk Server
- BizTalk Messaging servers, installing BizTalk Server
ms.assetid: 8aaa1b97-90f0-4317-9403-ac8b5b9f80e3
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2db4b3d5ff34a724b8b37a08f0bf60807d31a2b2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="installing-and-configuring-biztalk-server-on-the-messaging-server"></a><span data-ttu-id="e0ba0-102">安装和消息传送的服务器上配置 BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="e0ba0-102">Installing and Configuring BizTalk Server on the Messaging Server</span></span>
<span data-ttu-id="e0ba0-103">本部分介绍如何安装和配置[!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)]用作消息的服务器用于连接到 SWIFT 网络。</span><span class="sxs-lookup"><span data-stu-id="e0ba0-103">This section describes how to install and configure [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)] to be used as the messaging server for connecting to the SWIFT network.</span></span>  
  
### <a name="to-install-and-configure-biztalk-server-on-the-messaging-server"></a><span data-ttu-id="e0ba0-104">若要安装和消息传送服务器上配置 BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="e0ba0-104">To install and configure BizTalk Server on the Messaging Server</span></span>  
  
1.  <span data-ttu-id="e0ba0-105">执行的自定义安装[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]选择除 EDI、 人工工作流服务 （工作流服务） 和 MRSR 站点的所有功能，除非所需的其他应用程序。</span><span class="sxs-lookup"><span data-stu-id="e0ba0-105">Perform a custom installation of [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] choosing all the features except EDI, Human Workflow Services (HWS), and MRSR site, unless required by other applications.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e0ba0-106">请注意，在单台计算机部署中，此计算机是一个运行 HTTP 前端服务所在的计算机。</span><span class="sxs-lookup"><span data-stu-id="e0ba0-106">Note that in single-computer deployment, this computer is the same computer as the one that runs the HTTP front-end service.</span></span>  
  
2.  <span data-ttu-id="e0ba0-107">执行配置[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="e0ba0-107">Perform configuration of [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e0ba0-108">不安装消息队列，因为我们将安装[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]MSMQ 称为 MSMQT 版本。</span><span class="sxs-lookup"><span data-stu-id="e0ba0-108">Do not install Message Queuing, because we will be installing the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] version of MSMQ known as MSMQT.</span></span> <span data-ttu-id="e0ba0-109">有关 MSMQT 的详细信息，请参阅 BizTalk 消息队列适配器 (MSMQT) 配置 MSDN 网站上在[http://go.microsoft.com/fwlink/?LinkID=48875](http://go.microsoft.com/fwlink/?LinkID=48875)。</span><span class="sxs-lookup"><span data-stu-id="e0ba0-109">For more information about MSMQT, see BizTalk Message Queuing Adapter (MSMQT) Configuration on the MSDN Web site at [http://go.microsoft.com/fwlink/?LinkID=48875](http://go.microsoft.com/fwlink/?LinkID=48875).</span></span>  
  
3.  <span data-ttu-id="e0ba0-110">安装所需的任何其他修补程序[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]为可安装指南中。</span><span class="sxs-lookup"><span data-stu-id="e0ba0-110">Install any additional hotfixes required by [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)] as available in the installation guide.</span></span> <span data-ttu-id="e0ba0-111">在此发布时，没有任何所需的修补程序。</span><span class="sxs-lookup"><span data-stu-id="e0ba0-111">At the time of this publication, there are no required hotfixes.</span></span>