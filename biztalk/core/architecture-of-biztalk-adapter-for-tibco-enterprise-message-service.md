---
title: 用于 TIBCO Enterprise Message Service 的 BizTalk 适配器的体系结构 |Microsoft Docs
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
ms.openlocfilehash: 8d1f6735ec5fee445fa5f2403f7ca48d32dfae2e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65359015"
---
# <a name="architecture-of-biztalk-adapter-for-tibco-enterprise-message-service"></a>用于 TIBCO Enterprise Message Service 的 BizTalk 适配器的体系结构
用于 TIBCO Enterprise Message Service (EMS) 的 Microsoft BizTalk 适配器提供了一种方法来交换 TIBCO EMS 系统和 BizTalk Server 之间的实时业务数据。 适配器允许 XML 应用程序与 TIBCO EMS 之间的交互。  
  
 适配器接受 XML 消息，使 BizTalk 应用程序与 TIBCO EMS 使用以下方法之一进行通信：  
  
-   **传输适配器**:使用静态单向发送端口将消息发送到 TIBCO EMS。  
  
-   **接收适配器**:使用静态单向接收端口以接收来自 TIBCO EMS 的消息。  
  
## <a name="one-way-send-operation"></a>单向发送操作  
 下图显示了使用用于 TIBCO EMS 的 BizTalk 适配器的单向发送操作的体系结构。  
  
 ![](../core/media/tibcoems-architecture-send.gif "TIBCOEMS_architecture_send")  
  
## <a name="one-way-receive-operation"></a>单向接收操作  
 下图显示了体系结构进行的单向接收操作使用用于 TIBCO EMS 的 BizTalk 适配器。  
  
 ![](../core/media/tibcoems-architecture-receive.gif "TIBCOEMS_architecture_receive")  
  
## <a name="see-also"></a>请参阅  
 [适配器功能](../core/adapter-features.md)   
 [规划和体系结构](../core/planning-and-architecture16.md)