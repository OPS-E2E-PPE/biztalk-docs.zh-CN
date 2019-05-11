---
title: 支持的适配器 XSD 元素类型 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 00691a9e-434f-4baa-9a01-b6f452758ab3
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 26188811127c431e6bbe67c28c7806558b8ec7a8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396631"
---
# <a name="supported-adapter-xsd-element-types"></a>支持的适配器 XSD 元素类型
下表列出了适配器框架支持的元素。 在配置架构中定义新元素时，使用以下类型的任何替换`string`在下面的示例：  
  
```  
<xs:element name="uri" type="xs:string">  
```  
  
|类型|XML 类型|UI 行为|其他详细信息|  
|----------|--------------|-----------------|---------------------|  
|string|None|编辑框中只接受键入。|若要将限制最大/最小值的属性|  
|normalizedString|None|编辑框中只接受键入。|若要将限制最大/最小值的属性|  
|integer|None|编辑框中只接受键入。|若要将限制最大/最小值的属性|  
|positiveInteger|None|编辑框中只接受键入。|若要将限制最大/最小值的属性|  
|negativeInteger|None|编辑框中只接受键入。|若要将限制最大/最小值的属性|  
|nonNegativeInteger|None|编辑框中只接受键入。|若要将限制最大/最小值的属性|  
|nonPositiveInteger|None|编辑框中只接受键入。|若要将限制最大/最小值的属性|  
|ssNoversion|None|编辑框中只接受键入。|若要将限制最大/最小值的属性|  
|unsignedInt|None|编辑框中只接受键入。|若要将限制最大/最小值的属性|  
|long|None|编辑框只接受键入和十进制数字。|若要将限制最大/最小值的属性|  
|unsignedLong|None|编辑框只接受键入和十进制数字。|约束最大/最小值的属性|  
|short|None|编辑框中只接受键入。|若要将限制最大/最小值的属性|  
|unsignedShort|None|编辑框中只接受键入。|若要将限制最大/最小值的属性|  
|Decimal|None|编辑框中只接受键入。|若要将限制最大/最小值的属性|  
|FLOAT|None|编辑框中只接受键入。|若要将限制最大/最小值的属性|  
|double|None|编辑框中只接受键入。|若要将限制最大/最小值的属性|  
|boolean|None|填充有布尔值的下拉列表。|None|  
|time|None|编辑框中只接受键入。|None|  
|dateTime|None|编辑框中只接受键入。 在字段区域的最后阶段显示一个省略号。 单击省略号，然后就会显示日历。|None|  
|date|None|编辑框中只接受键入。 在字段区域的最后阶段显示一个省略号。 单击省略号，然后就会显示日历。|None|  
|gMonth|None|编辑框中只接受键入。|此值是一个字符串，因此可能无法按预期运行。 请考虑使用 xsd: int 类型进行限制，若要保存的月份值。|  
|gYear|None|编辑框中只接受键入。|此值是一个字符串，因此可能无法按预期运行。 请考虑使用 xsd: int 类型进行限制，若要保存的年份值。|  
|gYearMonth|None|编辑框中只接受键入。|此值是一个字符串，因此可能无法按预期运行。 请考虑使用 xsd: int 类型进行限制，若要保存的年份和月份值。|  
|gDay|None|编辑框中只接受键入。|此值是一个字符串，因此可能无法按预期运行。 请考虑使用 xsd: int 类型具有限制，以改为保存的日期值。|  
|gMonthDay|None|编辑框中只接受键入。|此值是一个字符串，因此可能无法按预期运行。 请考虑使用 xsd: int 类型进行限制，若要保存的月份和日期值。|  
|“属性”|None|编辑框中只接受键入。|None|  
|NCName|None|编辑框中只接受键入。|None|  
|anyURI|None|编辑框中只接受键入。|None|  
|序列|"Sequence"架构元素|None|None|  
|组|None|一个"+"或"-"符号来展开或折叠组中的所有字段。<br /><br /> 在属性页右侧无编辑功能。|None|  
|文件名|FileName|在字段区域的最后阶段显示一个省略号。 单击省略号并**Windows FileOpen**对话框随即出现，可以选择一个文件。|None|  
|文件夹名|FolderName|在字段区域的最后阶段显示一个省略号。 单击省略号并**Windows 文件夹打开**对话框可以选择一个文件夹。|None|  
|SSO 应用程序 ID|SSOAppID|使用 SSO 应用程序列表填充的下拉列表|None|  
|Password|Password|编辑框使用"*"而不明文形式显示。|None|  
  
## <a name="see-also"></a>请参阅  
 [适配器设计问题](../core/adapter-design-issues.md)