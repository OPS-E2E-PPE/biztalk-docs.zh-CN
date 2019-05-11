---
title: Functoid 类别 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 029905e2-f01a-436a-b2ed-a364379c9cc5
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0d71180b97cbad95dfcb19798dd46bdc3b1a9057
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65345249"
---
# <a name="functoid-categories"></a>Functoid 类别
BizTalk functoid 分为根据其预期用途的类别。 例如，数据库 functoid 用于在运行时从数据库提取数据，数学 functoid 用于执行数学运算，等等。 在 BizTalk 映射器 functoid 按类别显示在[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]工具箱。 

## <a name="categories--description"></a>类别和说明
下表显示了 functoid 类别中，简要描述了类别，并在每个类别，其中包括指向其相应的参考页中显示的 functoid 列表。  
  
|Functoid 类别 <br/><br/> 类别说明|Functoid 类别中|  
|---|---|  
|**高级** <br /><br /> 主要与循环记录一起使用。 此外用于运行任意脚本或编译代码。|添加、 索引、 迭代、 循环、 批量复制、 Nil 值、 记录计数、 脚本、 表提取程序、 表循环、 值映射、 值映射 （平展）|  
|**转换** <br /><br /> 用于将转换到和从 ASCII，和数值进制之间。|ASCII 到字符、 字符到 ASCII、 十六进制、 八进制|  
|**累计** <br /><br /> 用于执行数学运算中循环记录，如平均值和进行串联。|累计平均、 累计连接、 累计最大、 累计最小、 累计和|  
|**“数据库”** <br /><br /> 用于从数据库中提取数据并在目标实例消息中使用它。|数据库查找、 错误返回格式化消息、 获取应用程序 ID、 获取应用程序值、 获取公用 ID、 获取公用值、 删除应用程序 ID、 设置公用 ID、 值提取程序|  
|**日期和时间** <br /><br /> 用于检索当前日期和时间，并计算增量时间。|添加天数、 日期、 日期和时间、 时间|  
|**逻辑** <br /><br /> 用于执行各种逻辑运算，例如大于和逻辑存在。|等于、 大于、 大于或等于、 IsNil、 小于、 小于或等于逻辑 AND、 日期判断、 存在判断、 判断、 逻辑不、 逻辑或、 字符串判断、 不等于|  
|**数学** <br /><br /> 用于执行各种数学运算，例如加法和乘法。|绝对值、 加法、 除法、 整数、 最大值、 最小值、 模、 乘法、 Round、 平方根、 减法|  
|**科学记数** <br /><br /> 用于执行各种科学计数法运算，例如对数和三角运算。|10 ^ n，反正切值、 指定底的对数、 常用对数、 余弦、 自然指数函数、 自然对数、 正弦、 正切值、 X ^ Y|  
|**String** <br /><br /> 用于执行各种字符串函数，例如裁剪和连接。|小写、 大小、 字符串连接、 字符串提取、 字符串查找、 左侧字符串、 字符串左侧空格裁剪、 右侧，字符串字符串右侧空格裁剪、 大写|  
  
> [!NOTE]
>  Functoid 的用途是从其名称通常明显。  
> 
> [!NOTE]
>  Microsoft 中附带的所有 functoid[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]是内联 C# 中，除**数据库**functoid。  
  
## <a name="see-also"></a>请参阅  
 [基本 Functoid](../core/basic-functoids.md)   
 [高级的 Functoid](../core/advanced-functoids.md)