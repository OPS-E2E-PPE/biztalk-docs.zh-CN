---
title: 交换控制编号序列已用尽的合作伙伴和 TPA |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e77c0574-bc51-4690-a7f6-5702f6486f05
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 19f1aeb79febf8bca10f46b2b5a3a5ba319f6028
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36989358"
---
# <a name="interchange-control-number-sequence-exhausted-for-partner-and-tpa"></a>交换控制编号序列的合作伙伴和 TPA 耗尽
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                                                                    |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                         [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                         |
| 产品版本 |                                                     [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                     |
|    事件 ID     |                                                                                 -                                                                                  |
|  事件源   |                                       [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI                                       |
|    组件    |                                                                             EDI 引擎                                                                             |
|  符号名称  |                                                                 EdiControlNumberExhaustedForParty                                                                  |
|  消息正文   | 为合作伙伴交换控制编号序列已用尽 '{1}对于 TPA{2}。 重置该序列中的{2}-使用 BizTalk Server 管理的 EDI 属性。 |
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明 BizTalk Server 无法处理文档，因为交换的控制范围已用完中协议{2}。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请选中该复选框以重置 {2} 协议的控制编号或增加控制编号范围，或者针对协议中的控制编号范围规范单击“重置”按钮。