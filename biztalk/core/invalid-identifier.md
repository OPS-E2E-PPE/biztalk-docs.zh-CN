---
title: 无效的标识符 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f87e1e42-457f-4d04-a1d2-6b796f3fa7b7
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0e277a1b2a02ee622f37007a2d2a001570bded79
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65381347"
---
# <a name="invalid-identifier"></a>无效的标识符
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                                                                           |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                            [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                             |
| 产品版本 |                                                        [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                                                         |
|    事件 ID     |                                                                                     0                                                                                     |
|  事件源   |                                                                                     0                                                                                     |
|    组件    |                                                                                     0                                                                                     |
|  符号名称  |                                                                                     0                                                                                     |
|  消息正文   | "{0}"不是有效标识符。 正在还原原始名称。 （是有效的标识符以字母开头后, 跟零个或多个字母或数字和不能包含空格。） |
  
## <a name="explanation"></a>解释  
 此错误表明发布一个架构不是有效的.net 标识符时定义的 web 方法。  
  
## <a name="user-action"></a>用户操作  
 将 web 方法重命名为有效的.net 标识符。 是有效的标识符以字母开头后, 跟零个或多个字母或数字，并且不能包含空格。