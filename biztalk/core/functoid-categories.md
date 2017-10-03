---
title: "Functoid 类别 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 029905e2-f01a-436a-b2ed-a364379c9cc5
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 89db4168af133e616f48ded54cce98cd54bb8ec8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="functoid-categories"></a>Functoid 类别
BizTalk functoid 根据其用途划分为不同的类别。 例如，数据库 functoid 用于在运行时从数据库中提取数据，数学 functoid 用于执行数学运算，等等。 在 BizTalk 映射程序 functoid 显示在中按类别[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]工具箱。 

## <a name="categories--description"></a>类别和说明
下表显示了 functoid 类别，对类别进行了简要描述，并显示各个类别的 functoid 列表，包括到其相应的参考页的链接。  
  
|Functoid 类别 <br/><br/> 类别说明|类别中的 Functoid|  
|---|---|  
|**高级** <br /><br /> 主要与循环记录一起使用。 也用于运行任意脚本或编译代码。|断言，索引，循环迭代中，批量复制、 Nil 值记录计数脚本，表提取程序表循环、 值映射，映射 （平展） 的值|  
|**转换** <br /><br /> 用于转换为 ASCII 以及从 ASCII 转换，以及在数值进制之间进行转换。|为字符的 ASCII 字符为 ASCII，十六进制、 八进制|  
|**累积** <br /><br /> 用于在循环记录中执行数学运算，例如求平均值和进行串联计算。|累计平均、 累积串联，累计最大值、 累计最小累计和|  
|**数据库** <br /><br /> 用于从数据中提取数据并在目标实例消息中使用该数据。|数据库查找，错误返回格式消息，获取应用程序 ID、 获取应用程序值、 获取常见 ID，获取公共值、 删除应用程序 ID，设置常见 ID，值提取程序|  
|**日期和时间** <br /><br /> 用于检索当前日期和时间，以及计算增量时间。|添加天、 日期、 日期和时间、 时间|  
|**逻辑** <br /><br /> 用于执行各种逻辑运算，例如大于和存在判断运算。|等于、 大于、 大于或等于、 IsNil，小于号、 小于或等于逻辑 AND、 逻辑日期、 逻辑存在、 逻辑数值、 逻辑不、 逻辑或、 逻辑字符串、 不等于|  
|**数学** <br /><br /> 用于执行各种数学运算，例如加法和乘法。|绝对值的数值、 添加、 除法、 整数、 最大值、 最小值，取模，乘法、 轮、 平方根、 减法|  
|**科学记数** <br /><br /> 用于执行各种科学计数法运算，例如对数和三角运算。|10 ^ n，反正切值、 指定底的对数，常用对数、 余弦值、 自然指数函数，自然对数、 正弦值、 正切值、 X ^ Y|  
|**字符串** <br /><br /> 用于执行各种字符串函数，例如裁剪和连接。|小写、 调整大小、 字符串串联、 左提取，字符串查找字符串的字符串、 字符串左侧空格裁剪和右侧，字符串字符串右剪裁，大写|  
  
> [!NOTE]
>  Functoid 的用途通常从名称中就可以看出来。  
  
> [!NOTE]
>  Microsoft 中包含的所有 functoid[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将以内联方式 C# 中，除**数据库**functoid。  
  
## <a name="see-also"></a>另请参阅  
 [基本 Functoid](../core/basic-functoids.md)   
 [高级的 Functoid](../core/advanced-functoids.md)