---
title: 授权限定符无效 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bc2a9f83-833f-4ea0-9421-7382ee1b1a54
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f893ed867b5783ee1bb9edde49f9f11bf55a7219
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36974022"
---
# <a name="invalid-authorization-qualifier"></a>授权限定符无效
## <a name="details"></a>详细信息  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  产品名称   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| 产品版本 |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    事件 ID     |                                           -                                            |
|  事件源   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI |
|    组件    |                                       EDI 引擎                                       |
|  符号名称  |                     X12Ta1InvalidAuthorizationQualifierDescription                     |
|  消息正文   |                            授权限定符无效                             |
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明接收管道无法处理传入的交换，因为 ISA01 中“授权限定符”的值与架构指定的任何枚举值都不匹配。 架构是 BaseArtifacts.dll 中的 X12ServiceSchema。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请确保 ISA01 标头中的值与 X12ServiceSchema 指定的其中一个枚举值匹配，然后重新发送交换。