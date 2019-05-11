---
title: 跨字段验证规则违反 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2d606a80-9046-4572-9cfb-a3434ed8073e
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e21c1f0ff73f1d3c26f6c1023c9bd221bf0625c5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65353474"
---
# <a name="cross-field-validation-rule-violated"></a>违反跨字段验证规则
## <a name="details"></a>详细信息  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  产品名称   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| 产品版本 |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    事件 ID     |                                           -                                            |
|  事件源   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI |
|    组件    |                                       EDI 引擎                                       |
|  符号名称  |                                           -                                            |
|  消息正文   |                          违反跨字段验证规则                          |
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明接收管道或发送管道中的 X12 交换未通过跨字段验证。 这表明 X12ConditionDesignator_Check 标志设置为“是”，并且至少交换中的一个元素未通过前缀“X12ConditionDesignatorX”标识的规则。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请执行以下操作之一：  
  
-   确定哪个数据元素未通过跨字段验证规则。 请与交换的发送方联系并且指出创建交换时必须遵循该规则。  
  
-   打开交换的架构，并将未通过验证的数据元素的 X12ConditionDesignator_Check 标志设置为“否”。