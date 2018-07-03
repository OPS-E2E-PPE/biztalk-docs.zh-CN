---
title: 比较运算符只能为 Equals、 NotEquals 和 Exists |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: aad902a2-d0dc-4d91-87a7-a6305e2f40e0
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 50499ea6ab9f002d36c213a8bca871884d3b077a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37023467"
---
# <a name="the-comparison-can-only-be-equals-notequals-and-exists"></a>比较运算符只能为 Equals、NotEquals 和 Exists
## <a name="details"></a>详细信息  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  产品名称   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| 产品版本 |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    事件 ID     |                                           -                                            |
|  事件源   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI |
|    组件    |                                       EDI 引擎                                       |
|  符号名称  |                                 Err_InvalidComparision                                 |
|  消息正文   |                比较运算符只能为 Equals、NotEquals 和 Exists。                |
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明 BizTalk Server 在尝试决定批处理消息时无法比较上下文属性。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请确保在活动的批处理中提供的筛选器没有指定除 Equals、 NotEquals 和 Exists 的 XSD 类型的不支持其他操作的运算符。