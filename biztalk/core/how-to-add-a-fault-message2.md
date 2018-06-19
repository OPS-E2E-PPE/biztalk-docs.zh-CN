---
title: 如何添加错误 Message2 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- fault messages, adding
- messages, fault messages
ms.assetid: 8f1b40af-2c75-4167-8b62-a86b791907c9
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6dee8a1fca0e30a96b6a714b5c717c0638bc8144
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22246453"
---
# <a name="how-to-add-a-fault-message"></a>如何添加错误消息
创建通向后端系统的端口时，该端口中包含了请求和响应通信。 您必须添加一个信息，以便您可以将其分配给故障。  
  
### <a name="to-add-a-fault-message"></a>添加错误消息  
  
1.  在**业务流程视图**窗口中，右键单击**消息**，然后选择**新消息**。  
  
     由此将创建 Message_3，您可将其明确分配给该错误。  
  
2.  右键单击 Message_3，然后选择**属性**。  
  
3.  在**属性**对话框中，设置**消息类型**。  
  
     选择 **.NET 类**，然后选择**SystemString**。  
  
## <a name="see-also"></a>另请参阅  
 [使用 BizTalk Server 异常处理](../core/using-biztalk-server-exception-handling3.md)