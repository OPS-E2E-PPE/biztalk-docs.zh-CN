---
title: 条件性必需数据元素缺失 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a5105c03-fa26-4c38-a276-c656f3076d5f
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 68e67804d10a1fc3f920f3fadfdfc3a0aff81cae
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65356526"
---
# <a name="conditional-required-data-element-missing"></a>条件性必需数据元素缺失
## <a name="details"></a>详细信息  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  产品名称   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| 产品版本 |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    事件 ID     |                                           -                                            |
|  事件源   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI |
|    组件    |                                       EDI 引擎                                       |
|  符号名称  |                 X12DeConditionalRequiredDataElementMissingDescription                  |
|  消息正文   |                       条件性必需数据元素缺失                        |
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明 EDI 接收管道无法处理传入的交换，因为交换中不存在 X12ConditionDesignatorX 规则所需的数据元素。  
  
## <a name="user-action"></a>用户操作  
 此错误可能是传入的交换出现了问题，而不是 BizTalk Server 的配置或操作出现了问题。 若要解决此错误，请与交换的发送方联系并指出他们需要更改交换中使用的字符或字段 UNB1.1 中标识的字符集以便它们相匹配。