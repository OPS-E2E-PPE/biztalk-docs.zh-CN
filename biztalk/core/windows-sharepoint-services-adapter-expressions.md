---
title: Windows SharePoint Services 适配器表达式 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- macros, Windows SharePoint Services adapters
- configuring [Windows SharePoint Services adapters], supported macros
- configuring [Windows SharePoint Services adapters], expressions
- Windows SharePoint Services adapters, expressions
ms.assetid: 15e3afb2-0ef8-41b4-b3ec-de84af738c12
caps.latest.revision: 22
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 553ed4526607a30141f9643f08a5afa11c5bc538
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65240337"
---
# <a name="windows-sharepoint-services-adapter-expressions"></a>Windows SharePoint Services 适配器表达式
本主题介绍该格式，可以指定为值的字符串的含义**文件 NameProperty 源**Windows SharePoint Services 适配器的属性。 它还介绍了相关的上下文属性**WSS。文件名**和**WSS。ConfigPropertiesXml**。 两个表达式，可轻松地定义文件名值或自定义 Windows SharePoint 服务列值，基于文本，以及从消息或 BizTalk 系统中提取的值。  
  
 表达式可以包含文本和宏。 文本将显示文件名称中完全按照输入它们。 宏必须放在 %字符之间。 宏的一个示例是`%MessageID%`，在运行时将替换为消息的 GUID。  
  
> [!NOTE]
>  为文本或在 XPATH 使用 %字符时，它必须将其转义为这\\%。 单个 %将被视为宏分隔符，其中\\%将在运行时替换单个 %。 \ 字符必须转义为\\ \\。  
  
## <a name="expression-examples"></a>表达式示例  
  
|设计时间值|运行时值|  
|-----------------------|-------------------|  
|XYZ|XYZ|  
|PurchaseOrder|PurchaseOrder|  
|%MessageID%|55B93F27-7455-4066-ABE1-B4EBE6839A1A|  
|PurchaseOrder-%messageid%|PurchaseOrder - 55B93F27-7455-4066-ABE1-B4EBE6839A1A|  
|折扣\\%10|Discount %10|  
|PurchaseOrder-%XPATH=//ns0:PurchaseOrder/ns0:ID%|PurchaseOrder – 10001|  
|PurchaseOrder-%XPATH=//ns0:PurchaseOrder/ns0:PartnerName%-%XPATH=//ns0:PurchaseOrder/ns0:ID%|PurchaseOrder – Contoso-10001|  
  
## <a name="supported-macros"></a>受支持的宏  
  
|设计时间值|运行时值|  
|-----------------------|-------------------|  
|%MessageID%|BizTalk 消息 ID 是唯一的 GUID。|  
|%SendingOrchestrationID%|BizTalk 作为消息起源的业务流程实例的 ID。|  
|%SendingOrchestrationType%|作为消息起源的业务流程类型名称。|  
|%XPATH=\<xpath\>%|允许指定要用于从消息中提取值的 XPATH。 "\<xpath\>"必须替换为有效的 XPATH 表达式。 **注意：** Namespace 别名或 WSS 中的表达式之外，必须定义命名空间别名。ConfigNamespaceAliases 字段。|  
|%Filename%|替换为从消息上下文属性 WSS 中提取的文件名值。文件名。 从 SharePoint 接收的消息具有 WSS。文件名上下文属性值设置为 SharePoint 文件的名称。 使用 path.getfilenamewithoutextension 对返回的值进行预处理。 **注意：** 不能在 WSS 中使用此宏。配置 * 上下文属性 （从业务流程）。|  
|%Extension%|替换为从消息上下文属性 WSS 中提取的文件扩展名值。文件名。 从 SharePoint 接收的消息具有 WSS。文件名上下文属性值设置为 SharePoint 文件的名称。 使用 path.getextension 对返回的值进行预处理。 返回的值将不包含"。"。 **注意：** 不能在 WSS 中使用此宏。配置 * 上下文属性 （从业务流程）。|  
  
 支持的属性升级的任何有效表达式是有效的设计时文件名称。 设计时文件名将在运行时扩展为 Windows SharePoint Services 文件的名称。 此 Windows SharePoint Services 文件名具有某些其他限制，如下所述：  
  
-   有效的 Windows 文件名可以包含以下除外的任何 Unicode 字符: / \: *？  < > &#124; "# {} %& ~ 或制表符以及多个时间段。  
  
-   不能超过 256 个字符的文件名和完整的 URL 必须是小于或等于 256 个字符。  
  
-   如果 Windows SharePoint Services 文件扩展名包含无效字符，或者如果展开的文件名称或 URL 太长，将应用程序事件日志中记录错误和消息将被挂起。 错误和消息状态也将使用消息事件和服务实例跟踪的组中心页中可见。  
  
## <a name="see-also"></a>请参阅  
 [如何配置 Windows SharePoint Services 接收位置](../core/how-to-configure-a-windows-sharepoint-services-receive-location.md)   
 [如何配置 Windows SharePoint Services 发送处理程序](../core/how-to-configure-a-windows-sharepoint-services-send-handler.md)   
 [如何配置 Windows SharePoint Services 发送端口](../core/how-to-configure-a-windows-sharepoint-services-send-port.md)   
 [Windows SharePoint Services 适配器属性参考](../core/windows-sharepoint-services-adapter-properties-reference.md)   
 [支持的 Windows SharePoint Services 栏类型](../core/supported-windows-sharepoint-services-column-types.md)