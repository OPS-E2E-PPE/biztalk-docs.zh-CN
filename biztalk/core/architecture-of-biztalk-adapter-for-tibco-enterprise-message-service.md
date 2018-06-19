---
title: BizTalk 适配器 TIBCO 企业消息服务的体系结构 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- transmit adapter
- one-way receive operations
- architecture
- one-way send operations
- receive adapter
ms.assetid: 304c7236-aacd-4761-8c33-e876b53e84ff
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 88c7bc6420efb67085e4f3a05f6daf0c5dbd2feb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22230277"
---
# <a name="architecture-of-biztalk-adapter-for-tibco-enterprise-message-service"></a>用于 TIBCO Enterprise Message Service 的 BizTalk 适配器的体系结构
用于 TIBCO Enterprise Message Service (EMS) 的 Microsoft BizTalk 适配器提供在 TIBCO EMS 系统和 BizTalk Server 之间交换实时业务数据的方式。 该适配器能够在 XML 应用程序和 TIBCO EMS 之间进行交互。  
  
 该适配器使用下列适配器之一接受使 BizTalk 应用程序与 TIBCO EMS 进行通信的 XML 消息：  
  
-   **传输适配器**： 使用静态单向发送端口将消息发送到 TIBCO EMS。  
  
-   **接收适配器**： 使用静态单向接收端口从 TIBCO EMS 接收消息。  
  
## <a name="one-way-send-operation"></a>单向发送操作  
 下图显示使用用于 TIBCO EMS 的 BizTalk 适配器进行的单向发送操作的体系结构。  
  
 ![](../core/media/tibcoems-architecture-send.gif "TIBCOEMS_architecture_send")  
  
## <a name="one-way-receive-operation"></a>单向接收操作  
 下图显示使用用于 TIBCO EMS 的 BizTalk 适配器进行的单向接收操作的体系结构。  
  
 ![](../core/media/tibcoems-architecture-receive.gif "TIBCOEMS_architecture_receive")  
  
## <a name="see-also"></a>另请参阅  
 [适配器功能](../core/adapter-features.md)   
 [规划和体系结构](../core/planning-and-architecture16.md)