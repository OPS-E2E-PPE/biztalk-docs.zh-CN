---
title: 从 SAP 系统以在 BizTalk 使用 mySAP 适配器发送 Idoc |Microsoft Docs
description: ''
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: aea8a5e9-d775-4d52-a434-c2908b53cd2d
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 47b194afbc0fff102c9c3a7017f24610234a88ac
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65372862"
---
# <a name="sending-idocs-from-an-sap-system"></a>从 SAP 系统发送 Idoc
若要完成 SAP 系统将从 SAP 系统的 IDOC 发送到外部应用程序上的高级任务。 请与您的 SAP 管理员联系以执行这些任务或请参阅 SAP 指南。  
  
## <a name="send-an-idoc-from-sap"></a>从 SAP 发送 IDOC  
  
1.  启动将 SAP GUI。  
  
2.  创建使用 BD54 事务的逻辑系统。  
  
3.  在使用 SM59 事务的 TCP/IP 连接中创建的 RFC 目标。  
  
4.  创建使用 WE21 事务的端口，并将其附加到的最后一步中创建的 RFC 目标。  
  
5.  创建合作伙伴配置文件具有必需的消息类型和 IDOC 类型使用 WE20 事务，然后将其附加到的最后一步中创建的端口。  
  
6.  通过连接到使用销售事务的端口的消息类型来维护分布式的模型。  
  
7.  生成中 SAP IDOC。 例如，使用 BD10 事务来触发 MATMAS IDOC。 有关其他事务以触发特定 Idoc 信息，请与您的 SAP 管理员联系。  

## <a name="view-transaction-ids-in-sap"></a>查看在 SAP 中的事务 Id
当[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]调用 tRFC 或 IDOC 到 SAP 系统，SAP 系统寄存器事务 ID (TID) 响应中发送。 在某些情况下，可能需要知道与 SAP 系统以响应从调用注册 TID [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。 例如，你可能想要标识工作 (LUW) 的逻辑单元上 SAP 系统以解决问题。  
  
 若要查看在 SAP 系统中的 Tid，必须使用 SM58 事务。 请联系您的 SAP 管理员或 SAP 指南有关此事务的详细信息，请参阅。 

## <a name="view-details-about-idocs-sent-and-received-from-sap"></a>查看有关发送和接收来自 SAP 的 Idoc 详细信息
使用[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]，可以将 IDOC 发送到 SAP 系统，也可以从 SAP 系统接收 IDOC。 若要跟踪的状态和视图的数据的 IDOC 发送或接收的 SAP 系统，可以使用 WE02 事务。 请联系您的 SAP 管理员，或有关此事务的详细信息的 SAP 指南，请参阅。  

  
## <a name="see-also"></a>请参阅  
 [特定的 SAP 适配器方案中使用 SAP GUI 执行任务](performing-tasks-using-the-sap-gui-for-specific-sap-adapter-scenarios.md)