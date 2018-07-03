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
# <a name="installing-and-configuring-biztalk-server-on-the-messaging-server"></a>安装和配置 BizTalk Server 消息传送的服务器上
本部分介绍如何安装和配置 BizTalk Server 以便用作消息传送服务器用于连接到 SWIFT 网络。  

### <a name="to-install-and-configure-biztalk-server-on-the-messaging-server"></a>若要安装和配置 BizTalk Server 消息传送服务器上  

1. 执行的自定义安装[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]选择除 EDI、 工作流服务 (HWS) 和 MRSR 站点之外的所有功能，除非所需的其他应用程序。  

   > [!NOTE]
   >  请注意，在单台计算机部署中，此计算机是作为一个运行 HTTP 前端服务在同一台计算机。  

2. 执行的配置[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。  

   > [!NOTE]
   >  不安装消息队列，因为我们将安装[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]称为 MSMQT 的 MSMQ 版本。 有关 MSMQT 的详细信息，请参阅 BizTalk 消息队列适配器 (MSMQT) 配置 MSDN Web 站点上[ http://go.microsoft.com/fwlink/?LinkID=48875 ](http://go.microsoft.com/fwlink/?LinkID=48875)。  

3. 安装所需的任何其他修补程序[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]安装指南中为可用。 在此发布时，没有所需的修补程序。
