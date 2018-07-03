---
title: 无效的版本标识符 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 504b0b16-7d23-45ef-ae2a-ce1962b83f34
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: de725a51ba89312c7cb394e249c1ef40353f256b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37022851"
---
# <a name="invalid-version-identifier"></a>版本标识符无效
## <a name="details"></a>详细信息  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  产品名称   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| 产品版本 |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    事件 ID     |                                           -                                            |
|  事件源   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI |
|    组件    |                                       EDI 引擎                                       |
|  符号名称  |                       X12Ta1InvalidVersionIdentifierDescription                        |
|  消息正文   |                               版本标识符无效                               |
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明接收管道无法处理传入的交换，因为交换中的版本标识符（X12 交换中的 GS08 字段或 EDIFACT 交换中的 UNG7 字段）不符合服务架构（BaseArtifacts.dll 中的 X12ServiceSchema 或 EdifactServiceSchema）建立的数据类型和位数。 GS08 字段必须是 X12_AN 数据类型并且必须介于 1 和 12 位之间。 UNG7.1 中的版本必须是 EDIFACT_AN 数据类型并且必须介于 1 和 3 位之间。 UNG7.2 中的版本必须是 EDIFACT_AN 数据类型并且必须介于 1 和 3 位之间。 UNG7.3 中的协会分配代码必须是 EDIFACT_AN 数据类型并且必须介于 1 和 6 位之间。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请确保 GS08 或 UNG7 中的版本符合架构指定的数据类型和位数，然后重新发送交换。