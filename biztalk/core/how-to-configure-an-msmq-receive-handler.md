---
title: 如何配置 MSMQ 接收处理程序 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- receive handlers, MSMQ adapters
- configuring [MSMQ adapters], receive handlers
- MSMQ adapters, receive handlers
ms.assetid: d6d82098-3a73-44e2-80d5-143f77e919cc
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 61741921363caa96acc2cb1a1e787ad1fbd41120
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65386424"
---
# <a name="how-to-configure-an-msmq-receive-handler"></a>如何配置 MSMQ 接收处理程序
使用以下过程来更改与 MSMQ 接收处理程序的主机程序关联。  
  
> [!NOTE]
>  只有一个接收处理程序，可以与关联的每个主机。  
  
### <a name="to-change-the-host-with-which-the-msmq-receive-handler-is-associated"></a>若要更改与 MSMQ 接收处理程序的主机是关联  
  
1.  在 BizTalk Server 管理控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**平台设置**，然后展开**适配器**。  
  
2.  在展开的适配器列表中，单击**MSMQ**，在右窗格中，右键单击你想要配置，接收处理程序，再单击**属性**。  
  
3.  在中**适配器处理程序属性**对话框中，在**常规**选项卡上，在**主机名**列表中，选择接收处理程序将关联的主机。  
  
4.  单击“确定” 。  
  
## <a name="see-also"></a>请参阅  
 [配置 MSMQ 适配器](../core/configuring-the-msmq-adapter.md)