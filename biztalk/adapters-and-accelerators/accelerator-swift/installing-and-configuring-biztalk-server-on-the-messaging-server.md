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
ms.openlocfilehash: 527b0d707d0f78672018f31e60ea54ac436e1db4
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
---
# <a name="installing-and-configuring-biztalk-server-on-the-messaging-server"></a>安装和消息传送的服务器上配置 BizTalk Server
本部分介绍如何安装和配置 BizTalk Server 用于连接到 SWIFT 网络用作消息的服务器。  
  
### <a name="to-install-and-configure-biztalk-server-on-the-messaging-server"></a>若要安装和消息传送服务器上配置 BizTalk Server  
  
1.  执行的自定义安装[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]选择除 EDI、 人工工作流服务 （工作流服务） 和 MRSR 站点的所有功能，除非所需的其他应用程序。  
  
    > [!NOTE]
    >  请注意，在单台计算机部署中，此计算机是一个运行 HTTP 前端服务所在的计算机。  
  
2.  执行配置[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。  
  
    > [!NOTE]
    >  不安装消息队列，因为我们将安装[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]MSMQ 称为 MSMQT 版本。 有关 MSMQT 的详细信息，请参阅 BizTalk 消息队列适配器 (MSMQT) 配置 MSDN 网站上在[http://go.microsoft.com/fwlink/?LinkID=48875](http://go.microsoft.com/fwlink/?LinkID=48875)。  
  
3.  安装所需的任何其他修补程序[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]为可安装指南中。 在此发布时，没有任何所需的修补程序。