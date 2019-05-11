---
title: 单一登录：事件 10854 |Microsoft Docs
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
ms.openlocfilehash: 14d15f5f4bf2a3347b87ef624366177be63672c6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65306677"
---
# <a name="single-sign-on-event-10854"></a>单一登录：事件 10854
## <a name="details"></a>详细信息  
  
|                 |                                                            |
|-----------------|------------------------------------------------------------|
|  产品名称   |                 企业单一登录                  |
| 产品版本 | [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)] |
|    事件 ID     |                           10854                            |
|  事件源   |                           ENTSSO                           |
|    组件    |                            不可用                             |
|  符号名称  |               ENTSSO_E_INVALID_STRING_FORMAT               |
|  消息正文   |     字符串格式不正确的此函数。      |
  
## <a name="explanation"></a>解释  
 字符串格式不正确的此函数。  
  
## <a name="user-action"></a>用户操作  
 正确的密码字符串的格式如下所述：  
  
 VT_BSTR 类型属性  
  
 分隔符是/（斜杠）  
  
 dc = 默认情况下 (无操作-不执行任何操作)  
  
 示例： dc /  
  
 （无变化-'Cat' 到 'Cat'）  
  
 uc = 大写  
  
 示例： uc /  
  
 （将密码更改为大写-'Cat' 到 'CAT'）  
  
 lc = 小写  
  
 示例： lc /  
  
 （将密码更改为小写-'Cat' 到 'cat'）  
  
 rc = 删除字符-后接计数和字符  
  
 示例： rc/2 / #@/  
  
 (删除字符 '#' 和 ' @' 密码-从C@t#' 到 'Ct')  
  
 sc = 的替换字符-后接计数和要替换的字符后, 跟替换字符  
  
 示例： sc/3/abc/def /  
  
 (删除字符 a、 b 和 c 中的密码和替换为与有 '，'e' 和 'f' 分别)  
  
 (到 'Cdt' 的 ' cat')  
  
 ps = 开始键盘-后接计数 （最小密码长度）、 单个键盘字符  
  
 示例： ps/8 / #/  
  
 （如果密码没有达到最少 8 个字符的长度，则以键盘字符 '#' 直到开始，将总 8 个字符）  
  
 (为 ###Cat' 的 ' cat')  
  
 pe = 结束键盘-后接计数 （最小密码长度）、 单个键盘字符  
  
 示例： pe/10 / $/  
  
 （如果密码没有达到最少 10 个字符的长度，则以键盘字符 '$' 直到结束，将 10 个字符总数）  
  
 (到 'Cat$ $$' 的 ' cat')  
  
 tr = 截断-字符串-后接计数的长度限制  
  
 示例： tr/11 /  
  
 (Cat123456789' 到 'Cat12345678);  
  
 在字符串中按顺序处理标记。  
  
 例如：  
  
 uc/rc/1/&/sc/2/#$/--/ps/8/&/tr/32/