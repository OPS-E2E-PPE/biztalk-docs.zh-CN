---
title: 无效的标识符 |Microsoft 文档
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
ms.openlocfilehash: 148b2c2d0b2ec4fb54e15fd8cb50b5dcf0af310a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22257229"
---
# <a name="invalid-identifier"></a>无效的标识符
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|产品版本|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|事件 ID|0|  
|事件源|0|  
|组件|0|  
|符号名称|0|  
|消息正文|"{0}"不是有效的标识符。 正在还原原始名称。 （是有效的标识符包含字母后跟零个或多个字母或数字，不能包含空格。）|  
  
## <a name="explanation"></a>解释  
 此错误指示定义时发布架构不是有效的.net 标识符的 web 方法。  
  
## <a name="user-action"></a>用户操作  
 将 web 方法重命名为有效的.net 标识符。 有效的标识符由一个字母后跟零个或多个字母或数字组成，但不能包含空格。