---
title: 如何将消息添加为 Exception2 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- exceptions, adding messages
- messages, exceptions
- exception handling, adding messages
- fault messages, adding
ms.assetid: 9d8a3801-78cd-4c18-8deb-3fbe4a49a2f9
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 57cd4e3e0cdcfe34dd172282ef83768eb63b93fa
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37000791"
---
# <a name="how-to-add-a-message-for-an-exception"></a>如何添加异常的消息
当你首次创建一个端口到后端系统时，它包含请求和响应。 您必须添加一个信息，以便您可以将其分配给故障。  
  
### <a name="to-add-a-fault-message"></a>添加错误消息  
  
1. 在中**业务流程视图**窗口中，右键单击**消息**，然后选择**新消息**。  
  
    由此将创建 Message_3，您可将其明确分配给该错误。  
  
2. 右键单击**Message_3**，然后选择**属性**。  
  
3. 设置**消息类型**，如下所示： 选择 **.NET 类**，然后选择**系统、 字符串**  
  
   ![](../core/media/jdeoneworld-03-addscope.gif "JdeOneWorld_03_addscope")  
  
## <a name="see-also"></a>请参阅  
 [使用 BizTalk Server 的异常处理](../core/using-biztalk-server-exception-handling1.md)