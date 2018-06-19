---
title: 支持的适配器 XSD 元素类型 |Microsoft 文档
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
ms.openlocfilehash: 3992ecface8fafacb5e1e616c930178ad0ce33a7
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
ms.locfileid: "22279389"
---
# <a name="supported-adapter-xsd-element-types"></a>受支持的适配器 XSD 元素类型
下表列出了适配器框架支持的元素。 当在配置架构中定义一个新的元素，使用以下类型的任何替换 `string` 在下面的示例︰  
  
```  
<xs:element name="uri" type="xs:string">  
```  
  
|类型|XML 类型|UI 行为|其他说明|  
|----------|--------------|-----------------|---------------------|  
|string|InclusionThresholdSetting|只接受键入的编辑框。|若要将限制最大/最小值的属性|  
|normalizedString|无|只接受键入的编辑框。|若要将限制最大/最小值的属性|  
|integer|无|只接受键入的编辑框。|若要将限制最大/最小值的属性|  
|positiveInteger|无|只接受键入的编辑框。|若要将限制最大/最小值的属性|  
|negativeInteger|无|只接受键入的编辑框。|若要将限制最大/最小值的属性|  
|nonNegativeInteger|InclusionThresholdSetting|只接受键入的编辑框。|若要将限制最大/最小值的属性|  
|nonPositiveInteger|无|只接受键入的编辑框。|若要将限制最大/最小值的属性|  
|int|InclusionThresholdSetting|只接受键入的编辑框。|若要将限制最大/最小值的属性|  
|unsignedInt|InclusionThresholdSetting|只接受键入的编辑框。|若要将限制最大/最小值的属性|  
|long|无|只能键入十进制数字的编辑框。|若要将限制最大/最小值的属性|  
|unsignedLong|无|只能键入十进制数字的编辑框。|约束最大值/最小值的属性|  
|short|无|只接受键入的编辑框。|若要将限制最大/最小值的属性|  
|unsignedShort|无|只接受键入的编辑框。|若要将限制最大/最小值的属性|  
|decimal|InclusionThresholdSetting|只接受键入的编辑框。|若要将限制最大/最小值的属性|  
|float|InclusionThresholdSetting|只接受键入的编辑框。|若要将限制最大/最小值的属性|  
|double|InclusionThresholdSetting|只接受键入的编辑框。|若要将限制最大/最小值的属性|  
|boolean|无|填充有布尔值的下拉列表。|无|  
|time|InclusionThresholdSetting|只接受键入的编辑框。|无|  
|dateTime|无|只接受键入的编辑框。 字段区域的末尾有一个省略号。 单击该省略号，将显示日历。|无|  
|date|无|只接受键入的编辑框。 字段区域的末尾有一个省略号。 单击该省略号，将显示日历。|无|  
|gMonth|无|只接受键入的编辑框。|此值是一个字符串，因此其表现可能和期望不同。 请考虑使用 xsd:int 类型，以对所保存的月份值进行限制。|  
|gYear|无|只接受键入的编辑框。|此值是一个字符串，因此其表现可能和期望不同。 请考虑使用 xsd:int 类型，以对所保存的年值进行限制。|  
|gYearMonth|InclusionThresholdSetting|只接受键入的编辑框。|此值是一个字符串，因此其表现可能和期望不同。 请考虑使用 xsd:int 类型，以对所保存的年和月份值进行限制。|  
|gDay|无|只接受键入的编辑框。|此值是一个字符串，因此其表现可能和期望不同。 请考虑使用 xsd:int 类型，以对所保存的日期值进行限制。|  
|gMonthDay|无|只接受键入的编辑框。|此值是一个字符串，因此其表现可能和期望不同。 请考虑使用 xsd:int 类型，以对所保存的月份和日期值进行限制。|  
|名称|无|只接受键入的编辑框。|无|  
|NCName|无|只接受键入的编辑框。|无|  
|anyURI|InclusionThresholdSetting|只接受键入的编辑框。|无|  
|序列|“Sequence”架构元素|无|InclusionThresholdSetting|  
|组|无|用来展开或折叠组中所有字段的“+”或“-”号。<br /><br /> “属性”页的右侧无编辑功能。|InclusionThresholdSetting|  
|文件名|FileName|字段区域的末尾有一个省略号。 单击省略号和 **Windows FileOpen** 出现对话框，允许的文件的选择。|无|  
|文件夹名称|FolderName|字段区域的末尾有一个省略号。 单击省略号和 **Windows 文件夹打开** 对话框中将显示并允许所选内容的文件夹。|InclusionThresholdSetting|  
|SSO App ID|SSOAppID|填充有 SSO 应用程序列表的下拉列表|InclusionThresholdSetting|  
|密码|密码|显示“*”号而非明文的编辑框。|InclusionThresholdSetting|  
  
## <a name="see-also"></a>另请参阅  
 [适配器设计问题](../core/adapter-design-issues.md)