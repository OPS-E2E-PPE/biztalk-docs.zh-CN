---
title: 如何构造中的基元.NET 类型的 Web 消息部件 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- creating, Web messages
- Web messages, Message Assignment shape [Orchestration Designer]
- Web messages, creating
- Message Assignment shape [Orchestration Designer], Web messages
- Web messages, parts
- Web messages, .NET types
ms.assetid: 1fe52412-d2bc-484c-8925-c7ff3ca7704b
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 991970d5b0d40da1ec00b54919d2742cfd48353c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22248021"
---
# <a name="how-to-construct-a-web-message-part-from-a-primitive-net-type"></a>如何从基元 .NET 类型构造 Web 消息部分
自.NET 的基元类型中使用创建的 Web 消息部分**消息分配**形状。 也可以通过使用 .NET 帮助程序类设置各个部分来从基元 .NET 类型创建 Web 消息部分。 通过使用一个.NET 类创建消息类型的详细信息，请参阅[在用户代码中构造消息](../core/constructing-messages-in-user-code.md)。  
  
### <a name="to-construct-a-web-message-part-from-a-primitive-net-type"></a>从基元 .NET 类型构造 Web 消息部分  
  
1.  与打开的业务流程，打开**工具箱**单击**BizTalk 业务流程**选项卡。  
  
2.  拖动**构造消息**形状上的与业务流程。  
  
3.  编辑**构造消息**属性以包含你创建的 Web 消息类型的消息实例。  
  
4.  拖动**消息分配**形状拖到**构造消息**形状。  
  
5.  双击**消息分配**形状以打开 BizTalk 表达式编辑器。  
  
6.  在 BizTalk 表达式编辑器框中，将 Web 消息类型的各个部分设置为其所需的值。  
  
     例如，以下代码将表达式设置为字符串：  
  
    ```  
    ItemAvailRequestInstance.Item_ID = "This is Item_ID.";  
    ```  
  
## <a name="see-also"></a>另请参阅  
 [构造 Web 消息](../core/constructing-web-messages.md)