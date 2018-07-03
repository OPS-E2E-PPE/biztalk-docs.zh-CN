---
title: 在深度找不到 End Element |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a1edb60a-122a-4fe9-8d73-96521fe7326b
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 91c2727be39d3d2656e118d593b0347038657f61
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36970182"
---
# <a name="an-end-element-could-not-be-found-at-depth"></a>在深度找不到 End Element
## <a name="details"></a>详细信息  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  产品名称   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| 产品版本 |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    事件 ID     |                                           -                                            |
|  事件源   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI |
|    组件    |                                       EDI 引擎                                       |
|  符号名称  |                               EndElementNotFoundAtDepth                                |
|  消息正文   |                     在深度结束元素{0}未找到                     |
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明 BizTalk Server 无法处理传出的交换，因为 XML 消息未通过验证。 XML 消息不包含标头或数据元素的结束标记。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请向 XML 消息中添加相应的结束标记或尾部，然后重新发送。