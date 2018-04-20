---
title: 单一登录： 事件 10854 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d8faed9d-5c7e-4b99-bcd9-ea5f670d5e72
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 42f9e9e761689b2ed21ec37acdbb8a63f1f88070
ms.sourcegitcommit: 36350889f318e1f7e0ac9506dc8df794d475bda6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/20/2018
---
# <a name="single-sign-on-event-10854"></a>单一登录： 事件 10854
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|產品名稱|企業單一登入|  
|產品版本|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|事件 ID|10854|  
|事件源|ENTSSO|  
|元件|不適用|  
|符号名称|ENTSSO_E_INVALID_STRING_FORMAT|  
|消息正文|对于此函数来说，此字符串格式不正确。|  
  
## <a name="explanation"></a>解释  
 对于此函数来说，此字符串格式不正确。  
  
## <a name="user-action"></a>用户操作  
 密码字符串的正确格式说明如下：  
  
 VT_BSTR 类型属性  
  
 分隔符是 /（斜杠）  
  
 dc = 默认情况（无操作-不执行任何操作）  
  
 示例︰ dc /  
  
 （无更改 - 'Cat' 到 'Cat'）  
  
 uc = 大写  
  
 示例︰ uc /  
  
 （将密码更改为大写 - 'Cat' 到 'CAT'）  
  
 lc = 小写  
  
 示例︰ lc /  
  
 （将密码更改为小写 - 'Cat' 到 'cat'）  
  
 rc = 删除字符 - 后接计数和字符  
  
 示例： rc/2 / #@/  
  
 (删除字符 '#' 和 ' @' 密码-从C@t# 到 Ct)  
  
 sc = 替换字符 - 后接计数、将被替换的字符、用来替换的字符  
  
 示例︰ sc/3/abc/def /  
  
 （删除密码中的 'a'、'b' 和 'c'，并分别以 'd'、'e' 和 'f' 替换）  
  
 （'Cat' 到 'Cdt'）  
  
 ps = 开始键盘 - 后接计数（最小密码长度）、单个键盘字符  
  
 示例︰ ps/8 / #/  
  
 （如果密码没有达到最少 8 个字符的长度，则以键盘字符 '#' 开始，直到总共达到 8 个字符）  
  
 （'Cat' 到 '#####Cat'）  
  
 pe = 结束键盘 - 后接计数（最小密码长度）、单个键盘字符  
  
 示例︰ pe/10 / $/  
  
 （如果密码没有达到最少 10 个字符的长度，则以键盘字符 '$' 结束，直到总共达到 10 个字符）  
  
 （'Cat' 到 'Cat$$$$$$$'）  
  
 tr = 截断 - 字符串长度限制 - 后接计数  
  
 示例︰ tr/11 /  
  
 （'Cat123456789' 到 'Cat12345678'）；  
  
 按照字符串中的顺序处理标记。  
  
 例如：  
  
 uc/rc/1/&/sc/2/#$/--/ps/8/&/tr/32/