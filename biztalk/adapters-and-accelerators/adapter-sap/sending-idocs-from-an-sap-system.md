---
title: "从 SAP 系统用于 mySAP 适配器 BizTalk 发送到的 Idoc |Microsoft 文档"
description: 
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: aea8a5e9-d775-4d52-a434-c2908b53cd2d
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 63f7d1ccdaa8cb6a4ee12ad1cc4263c487a164c5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="sending-idocs-from-an-sap-system"></a>从 SAP 系统发送到的 Idoc
在 SAP 系统将从 SAP 系统的 IDOC 发送到外部应用程序上完成的高级任务。 与您的 SAP 管理员联系以执行这些任务，或请参阅 SAP 指南。  
  
## <a name="send-an-idoc-from-sap"></a>从 SAP 发送 IDOC  
  
1.  启动 SAP GUI。  
  
2.  创建使用 BD54 事务的逻辑系统。  
  
3.  创建一个 RFC 目标中使用 SM59 事务的 TCP/IP 连接。  
  
4.  创建使用 WE21 事务的端口，并将其附加到的最后一步中创建的 RFC 目标。  
  
5.  创建合作伙伴配置文件具有必需的消息类型和 IDOC 类型使用 WE20 事务，然后将其附加到的最后一步中创建的端口。  
  
6.  通过连接到使用销售事务的端口的消息类型维护分布式的模型。  
  
7.  生成中 SAP IDOC。 例如，使用 BD10 事务来触发 MATMAS IDOC。 有关其他事务来触发特定 Idoc 信息，请与您的 SAP 管理员联系。  

## <a name="view-transaction-ids-in-sap"></a>SAP 中的视图事务 Id
当[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]调用 tRFC 或发送 IDOC 到 SAP 系统，SAP 系统寄存器事务 ID (TID) 在响应中。 在某些情况下，你可能需要知道与 SAP 系统以响应从调用注册 TID [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。 例如，你可能想要标识的工作 (LUW) 的逻辑单元上的 SAP 系统以解决问题。  
  
 若要查看 Tid SAP 系统中，你必须使用事务 SM58。 请与您的 SAP 管理员或者参考有关此事务的详细信息的 SAP 指南。 

## <a name="view-details-about-idocs-sent-and-received-from-sap"></a>查看有关发送和接收从 SAP Idoc 详细信息
使用[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]，可以将 IDOC 发送到 SAP 系统，也可以从某个 SAP 系统接收 IDOC。 若要跟踪某个 SAP 系统的状态和视图的数据的 IDOC 发送或接收，可以使用事务 WE02。 请与您的 SAP 管理员，或参阅有关此事务的详细信息的 SAP 指南。  

  
## <a name="see-also"></a>另请参阅  
 [对于特定 SAP 适配器方案中使用 SAP GUI 执行任务](performing-tasks-using-the-sap-gui-for-specific-sap-adapter-scenarios.md)