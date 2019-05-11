---
title: 无法从交换 (R2) 读取分隔符集 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 17bdd32e-d43f-4f59-af27-5d3054fd5432
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7208e9be2d8c5f28420151af060720f72eaa1913
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65390226"
---
# <a name="delimiter-set-could-not-be-read-from-the-interchange-r2"></a>无法从交换 (R2) 读取分隔符集
## <a name="details"></a>详细信息  

|                 |                                                                                                                           |
|-----------------|---------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                    [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                     |
| 产品版本 |                                [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                 |
|    事件 ID     |                                                             -                                                             |
|  事件源   |                  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI                   |
|    组件    |                                                        EDI 引擎                                                         |
|  符号名称  |                                                             -                                                             |
|  消息正文   | 无法从交换读取分隔符集。 从根节点缺少属性 DelimiterSetSerializedData。 |

## <a name="explanation"></a>解释  
 此错误表明交换不包含分隔符集值。  

## <a name="user-action"></a>用户操作  
 若要解决此错误，请执行以下操作之一：  

- 将分隔符集值添加到交换中，如下所示：  

  1.  打开消息。  

  2.  确定交换中是否存在 UNA 段。 如果不是 UNA 段，咨询合作伙伴以将 UNA 段添加到交换。  

- 输入分隔符值 EfactDelimiters 管道属性，如下所示：  

  1. 在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击接收位置或发送端口使用你想要设置的属性的管道。 单击 **“属性”**。  

  2. 单击你想要设置的属性的管道旁的省略号按钮 （...）。  

  3. 输入值的 UNA 分隔符为逗号分隔列表 （UNA1、 UNA2、 UNA3、 UNA4、 UNA5 和 UNA6），更改所需的默认值。 默认值如下所示：0x3A、 0x2B、 0x2C、 0x3F、 0x20、 0x27。  

  4. 单击“确定” 。
