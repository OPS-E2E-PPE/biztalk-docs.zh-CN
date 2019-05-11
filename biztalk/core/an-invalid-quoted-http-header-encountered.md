---
title: 无效的引用时遇到的 HTTP 标头 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bb530ee6-ec6a-4791-ae99-b9db426c0896
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ff1372dc2eea57843d6d671e617aeeb2b8e90dea
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65359340"
---
# <a name="an-invalid-quoted-http-header-encountered"></a>无效的引用 HTTP 标头时遇到
## <a name="details"></a>详细信息  
  
|                 |                                                                                                              |
|-----------------|--------------------------------------------------------------------------------------------------------------|
|  产品名称   |              [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]              |
| 产品版本 |                          [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                          |
|    事件 ID     |                                                      -                                                       |
|  事件源   |            [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI            |
|    组件    |                                                  AS2 引擎                                                  |
|  符号名称  |                                                      -                                                       |
|  消息正文   | 无效的引用时遇到的 HTTP 标头。  详细信息如下所示：标头名称:"{0}"标头值:"{1}" |
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明 AS2 接收管道或 AS2 发送管道无法处理 AS2 消息，因为 AS2 的名称-从或 AS2-To HTTP 标头消息中的不带引号正确。 标头名称是以适应一个空格、 反斜杠或在名称中的双引号引起来。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，引号中的规则的 AS2 消息的标头名称中所述在 RFC 4130 第 6.2，"AS2 系统标识符"节"基于 MIME 的安全对等业务数据交换使用 HTTP，Applicability Statement 2 (AS2)"。