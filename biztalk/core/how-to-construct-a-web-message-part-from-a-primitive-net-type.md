---
title: 如何构造 Web 消息部分从基元.NET 类型 |Microsoft Docs
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
ms.openlocfilehash: 9ab2390ea0e053fadcd275d8be7c1eea6ea6e903
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65340196"
---
# <a name="how-to-construct-a-web-message-part-from-a-primitive-net-type"></a>如何构造 Web 消息部分从基元.NET 类型
从基元.NET 类型中使用创建 Web 消息部分**消息赋值**形状。 或者，可以通过使用.NET 帮助程序类设置各个部分来从基元.NET 类型创建 Web 消息部分。 使用.NET 类创建消息类型的详细信息，请参阅[在用户代码中构造消息](../core/constructing-messages-in-user-code.md)。  
  
### <a name="to-construct-a-web-message-part-from-a-primitive-net-type"></a>若要构造 Web 消息部分从基元.NET 类型  
  
1.  与打开业务流程中，打开**工具箱**然后单击**BizTalk 业务流程**选项卡。  
  
2.  拖动**构造消息**向业务流程的形状。  
  
3.  编辑**构造的消息**属性以包含针对相应 Web 消息类型创建的消息实例。  
  
4.  拖动**消息赋值**形状拖至**构造消息**形状。  
  
5.  双击**消息赋值**形状以打开 BizTalk 表达式编辑器。  
  
6.  在 BizTalk 表达式编辑器框中为其所需的值设置 Web 消息类型的各个部分。  
  
     例如，下面的代码设置为字符串的表达式：  
  
    ```  
    ItemAvailRequestInstance.Item_ID = "This is Item_ID.";  
    ```  
  
## <a name="see-also"></a>请参阅  
 [构造 Web 消息](../core/constructing-web-messages.md)