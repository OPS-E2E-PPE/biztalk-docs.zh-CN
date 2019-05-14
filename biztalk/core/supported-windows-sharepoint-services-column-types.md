---
title: 支持的 Windows SharePoint Services 列类型 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- configuring [Windows SharePoint Services adapters], supported column types
- Windows SharePoint Services adapters, supported column types
ms.assetid: 14992f52-9d18-4321-9152-83c8a37751bc
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 686f521f8a31974919e83487e1f2d403c8682155
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396866"
---
# <a name="supported-windows-sharepoint-services-column-types"></a>支持的 Windows SharePoint Services 列类型
本主题介绍支持的 Windows SharePoint Services 适配器的 Windows SharePoint Services 列类型。 可以在消息中设置这些列类型的值。  

> [!NOTE]
>  适配器不会更新计算的列。  

## <a name="supported-types"></a>支持的类型  
 下表介绍了支持的列类型：  


|           UI 类型           | SharePoint 对象模型类型 |                    示例                    |                                                                                                                                                                                                                                                                            注释                                                                                                                                                                                                                                                                            |
|-----------------------------|------------------------------|----------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|     单个文本行     |       SPFieldType.Text       |                 单个行                  |                                                                                                                                                                                                                                                                              None                                                                                                                                                                                                                                                                              |
|   多行文本    |       SPFieldType.Note       | 第 1 行<br /><br /> 第 2 行<br /><br /> 第 3 行 |                                                                                                                                                                                                                                                                              None                                                                                                                                                                                                                                                                              |
|      选择下拉列表       |      SPFieldType.Choice      |                   ChoiceA                    |                                                                                                                                                                                                                                                 ChoiceA 来自以下可用选项 (ChoiceA、 ChoiceB、 ChoiceC)                                                                                                                                                                                                                                                 |
|    选择单选按钮     |      SPFieldType.Choice      |             #ChoiceB; #ChoiceC; #              |                                                                                                                                                                                                                 启用 ChoiceB 和 ChoiceC，禁用 ChoiceA （可用选项包括 ChoiceA、 ChoiceB、 ChoiceC）。 请使用; # 作为分隔符。                                                                                                                                                                                                                 |
|           Number            |      SPFieldType.Number      |                   123.456                    |                                                                                                                                                                                                                                                                              None                                                                                                                                                                                                                                                                              |
| 货币 USD （或任何其他） |     SPFieldType.Currency     |                    100.00                    |                                                                                                                                                                                                                                                                              None                                                                                                                                                                                                                                                                              |
|           查找            |      SPFieldType.Lookup      |                      1                       |                                                                                                                                                                                                                                                 数是引用列表内的项标识符。                                                                                                                                                                                                                                                  |
|            YesNo            |     SPFieldType.Boolean      |                      1                       |                                                                                                                                                                                                                                                                     1 = 是<br /><br /> 0 = 否                                                                                                                                                                                                                                                                     |
|    超链接或图片     |       SPFieldType.URL        |  http://www.microsoft.com Microsoft 网站上 |                                                                                                                                                                                                                  URL 与显示文本以“,”分隔。 "Microsoft Web Site"文本将指向的超链接 http://www.microsoft.com                                                                                                                                                                                                                   |
|        日期和时间        |     SPFieldType.DateTime     |             2005-02-11T10:05:04              | 由 XML 标准为 xs: datetime 定义的日期时间。 对于 dateTime 模式是 CCYY-MM-DDThh:mm:ss 其中 CC 表示世纪，YY 年份，MM 月和 DD 日，前面的可选前导负号 （-） 字符来表示负的数字。 负字符是否省略的正数 （+） 假定。 T 是日期/时间分隔符，hh、 mm 和 ss 分别表示小时、 分钟和秒。 这种表示形式可以被其后紧接"Z"指示 UTC 或时区。 |

## <a name="see-also"></a>请参阅  
 [如何配置 Windows SharePoint Services 接收位置](../core/how-to-configure-a-windows-sharepoint-services-receive-location.md)   
 [如何配置 Windows SharePoint Services 发送处理程序](../core/how-to-configure-a-windows-sharepoint-services-send-handler.md)   
 [如何配置 Windows SharePoint Services 发送端口](../core/how-to-configure-a-windows-sharepoint-services-send-port.md)   
 [如何创建发送端口](../core/how-to-create-a-send-port2.md)   
 [Windows SharePoint Services 适配器属性参考](../core/windows-sharepoint-services-adapter-properties-reference.md)   
 [Windows SharePoint Services 适配器表达式](../core/windows-sharepoint-services-adapter-expressions.md)