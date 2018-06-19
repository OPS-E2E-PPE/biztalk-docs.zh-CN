---
title: 因为它未能通过验证正在挂起 batch 元素 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ea5e19e8-4592-40f4-bffe-85ab27653fd5
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7022041d8d47e1bfa52eb7ef45764c17ed1a2d8d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22279557"
---
# <a name="the-batch-element-is-being-suspended-as-it-failed-validation"></a>因为验证失败，批元素被挂起
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|产品版本|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|事件 ID|-|  
|事件源|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|组件|批处理引擎|  
|符号名称|BatchElementSuspended|  
|消息正文|因为验证失败，批元素被挂起。 错误的原因在于： {0}|  
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件指示批处理的业务流程无法添加事务设置为批处理的交换，因为事务集未由批处理业务流程执行验证。 将无事务集未通过验证需生成的交换。 批处理的业务流程设置 EDI。BatchElementValidationFailure 上下文属性设置为"True"。 BatchSuspend 业务流程根据该上下文属性提取消息，发布错误信息，然后就会被挂起。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请指出发生错误的事务集的发送方，如错误消息中所示。 让发送方解决导致其未通过验证的问题，然后重新发送该事务集。