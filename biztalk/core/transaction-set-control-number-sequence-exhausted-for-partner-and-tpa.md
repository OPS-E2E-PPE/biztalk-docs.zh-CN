---
title: 事务集控制编号序列的合作伙伴和 TPA 耗尽 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 67f194ca-3e0f-4ad4-8bc8-88aa7e5193a7
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 89f917dc3688755816c29dea82ae153133dcca05
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65279706"
---
# <a name="transaction-set-control-number-sequence-exhausted-for-partner-and-tpa"></a>事务集控制编号序列的合作伙伴和 TPA 耗尽
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                                                                        |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                           [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                           |
| 产品版本 |                                                       [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                       |
|    事件 ID     |                                                                                   -                                                                                    |
|  事件源   |                                         [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI                                         |
|    组件    |                                                                               EDI 引擎                                                                               |
|  符号名称  |                                                                   EdiControlNumberExhaustedForParty                                                                    |
|  消息正文   | 事务集控制编号序列已用尽 '{1}对于 TPA{2}。 重置该序列中的{2}-使用 BizTalk Server 管理的 EDI 属性。 |
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明 BizTalk Server 无法处理文档因为的事务集控制范围已经用尽中协议{2}。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请选中该复选框以重置的控制编号{2}协议或增加控制编号范围，或者在协议中命中根据控制编号范围规范的重置按钮。