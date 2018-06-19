---
title: 支持的 Windows SharePoint Services 列类型 |Microsoft 文档
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
ms.openlocfilehash: e5328c5dade3f02c480b58c36ff2cfdf9a5e7493
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22278869"
---
# <a name="supported-windows-sharepoint-services-column-types"></a>支持的 Windows SharePoint Services 列类型
本主题介绍了 Windows SharePoint Services 适配器所支持的 Windows SharePoint Services 列类型。 这些列类型的值可以在消息中进行设置。  
  
> [!NOTE]
>  该适配器不会更新计算列。  
  
## <a name="supported-types"></a>支持的类型  
 下表对所支持的列类型进行了介绍：  
  
|UI 类型|SharePoint 对象模型类型|示例|注释|  
|-------------|----------------------------------|------------|--------------|  
|单行文本|SPFieldType.Text|单个行|无|  
|多行文本|SPFieldType.Note|第 1 行<br /><br /> 第 2 行<br /><br /> 第 3 行|无|  
|选择下拉列表|SPFieldType.Choice|ChoiceA|ChoiceA 来自以下可用选项：ChoiceA、ChoiceB、ChoiceC|  
|选择单选按钮|SPFieldType.Choice|#ChoiceB;#ChoiceC;#|启用 ChoiceB 和 ChoiceC，禁用 ChoiceA（可用选项包括 ChoiceA、ChoiceB、ChoiceC）。 使用 ;# 作为分隔符。|  
|Number|SPFieldType.Number|123.456|无|  
|货币 USD（或任何其他货币）|SPFieldType.Currency|100.00|无|  
|查找|SPFieldType.Lookup|1|该数字是引用的列表内部的项标识符。|  
|YesNo|SPFieldType.Boolean|1|1=是<br /><br /> 0=否|  
|超链接或图片|SPFieldType.URL|http://www.microsoft.com, Microsoft 网站|URL 与显示文本以“,”分隔。 “Microsoft 网站”文本将为指向 http://www.microsoft.com 的超链接|  
|日期和时间|SPFieldType.DateTime|2005-02-11T10:05:04|日期时间由 XML 标准为 xs:dateTime 定义。 日期时间的模式为 CCYY-MM-DDThh:mm:ss，其中 CC 表示世纪，YY 表示年，MM 表示月，DD 表示日，前面的可选负号 (-) 字符表示负数。 如果省略负数字符，则假定为正数 (+)。 T 为日期/时间分隔符，hh、mm 和 ss 分别表示小时、分钟和秒。 此表示法后面可能紧跟“Z”，以表示 UTC 或时区。|  
  
## <a name="see-also"></a>另请参阅  
 [如何配置 Windows SharePoint Services 接收位置](../core/how-to-configure-a-windows-sharepoint-services-receive-location.md)   
 [如何配置 Windows SharePoint Services 发送处理程序](../core/how-to-configure-a-windows-sharepoint-services-send-handler.md)   
 [如何配置 Windows SharePoint Services 发送端口](../core/how-to-configure-a-windows-sharepoint-services-send-port.md)   
 [如何创建发送端口](../core/how-to-create-a-send-port2.md)   
 [Windows SharePoint Services 适配器属性参考](../core/windows-sharepoint-services-adapter-properties-reference.md)   
 [Windows SharePoint Services 适配器表达式](../core/windows-sharepoint-services-adapter-expressions.md)