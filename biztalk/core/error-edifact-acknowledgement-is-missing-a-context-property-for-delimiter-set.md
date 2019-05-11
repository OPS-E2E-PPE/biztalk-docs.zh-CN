---
title: 系统生成了 EDIFACT 确认。 但是，缺少分隔符集的上下文属性。 无法序列化 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8d7b1e62-3230-4cdc-830f-3267de1efd1c
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 959be3b06db82d4bd0ca741076adaa9df7148d70
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389336"
---
# <a name="the-edifact-acknowledgement-was-generated-by-the-system-however-it-is-missing-a-context-property-for-delimiter-set-it-cannot-be-serialized"></a>系统生成了 EDIFACT 确认。 但是，缺少分隔符集的上下文属性。 无法对其进行序列化
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                                               |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                              [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                               |
| 产品版本 |                                          [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                           |
|    事件 ID     |                                                                       -                                                                       |
|  事件源   |                            [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI                             |
|    组件    |                                                                  EDI 引擎                                                                   |
|  符号名称  |                                                                       -                                                                       |
|  消息正文   | 系统生成了 EDIFACT 确认。 但是，缺少分隔符集的上下文属性。 无法对其进行序列化 |
  
## <a name="explanation"></a>解释  
 此错误表明 BizTalk Server 无法序列化 EDIFACT 确认，并且 BizTalk 消息中缺少分隔符集上下文属性。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请确保将分隔符集上下文属性写入到 EDIFACT 确认的 BizTalk 消息上下文中。