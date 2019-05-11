---
title: 如何添加容错 Message2 |Microsoft Docs
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
ms.openlocfilehash: 8835098f95c34b506714306afd4c5e7fc42d1b63
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387362"
---
# <a name="how-to-add-a-fault-message"></a>如何添加错误消息
在创建后端系统的端口时，它包含请求和响应。 必须添加一条消息，以便可以将其分配给该错误。  
  
### <a name="to-add-a-fault-message"></a>若要添加错误消息  
  
1.  在中**业务流程视图**窗口中，右键单击**消息**，然后选择**新消息**。  
  
     这将创建 Message_3，您可以将其分配特定于该错误。  
  
2.  右键单击 Message_3，然后选择**属性**。  
  
3.  在中**属性**对话框中，将**消息类型**。  
  
     选择 **.NET 类**，然后选择**SystemString**。  
  
## <a name="see-also"></a>请参阅  
 [使用 BizTalk Server 的异常处理](../core/using-biztalk-server-exception-handling3.md)