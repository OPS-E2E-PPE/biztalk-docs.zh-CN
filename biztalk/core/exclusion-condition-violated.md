---
title: 违反排除条件 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0e508da6-7edc-45c0-a7ab-f23337dc1b54
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 93e55595eaf2903ead7319b5f0269f803a3a83e5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36968734"
---
# <a name="exclusion-condition-violated"></a>违反排除条件
## <a name="details"></a>详细信息  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  产品名称   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| 产品版本 |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    事件 ID     |                                           -                                            |
|  事件源   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI |
|    组件    |                                       EDI 引擎                                       |
|  符号名称  |                       X12DeExclusionConditionViolatedDescription                       |
|  消息正文   |       违反排除条件，请参见实例中的字段值以了解详细信息       |
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明在接收端或发送端，在设计时（使用 XML 验证工具）或在运行时对 X12 交换的验证失败，因为实例中的某个分段未通过跨字段验证排除规则。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请确保更改未通过排除规则的该分段，以便该分段通过跨字段验证，然后再次运行验证过程。