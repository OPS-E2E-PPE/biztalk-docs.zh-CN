---
title: "Windows SharePoint Services 适配器表达式 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- macros, Windows SharePoint Services adapters
- configuring [Windows SharePoint Services adapters], supported macros
- configuring [Windows SharePoint Services adapters], expressions
- Windows SharePoint Services adapters, expressions
ms.assetid: 15e3afb2-0ef8-41b4-b3ec-de84af738c12
caps.latest.revision: "22"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 377859a1b2c28774342c6ff9dc5cc312c9fd82d9
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="windows-sharepoint-services-adapter-expressions"></a>Windows SharePoint Services 适配器表达式
本主题介绍该格式，可以指定为值的字符串的含义**文件 NameProperty 源**Windows SharePoint Services 适配器的属性。 它还介绍相关的上下文属性中， **WSS。Filename**和**WSS。ConfigPropertiesXml**。 这些表达式使您很容易基于文本以及从消息或 BizTalk 系统提取的值来定义文件名值，或自定义 Windows SharePoint 服务列值。  
  
 表达式可以包含文本和宏。 文本将按键入顺序原样显示在文件名中。 宏必须放在“%”字符之间。 宏的示例如下：`%MessageID%`，在运行时该宏将替换为消息的 GUID。  
  
> [!NOTE]
>  当为文本或 XPATH 中使用 %字符时，它必须进行转义如下\\%。 单个 %将被视为宏分隔符，其中\\由单个 %，将在运行时替换 %。 \ 必须转义的字符如下\\ \\。  
  
## <a name="expression-examples"></a>表达式示例  
  
|设计时值|运行时值|  
|-----------------------|-------------------|  
|XYZ|XYZ|  
|PurchaseOrder|PurchaseOrder|  
|%MessageID%|55B93F27-7455-4066-ABE1-B4EBE6839A1A|  
|PurchaseOrder - %MessageID%|PurchaseOrder - 55B93F27-7455-4066-ABE1-B4EBE6839A1A|  
|折扣\\%10|折扣 %10|  
|PurchaseOrder - %XPATH=//ns0:PurchaseOrder/ns0:ID%|PurchaseOrder – 10001|  
|PurchaseOrder - %XPATH=//ns0:PurchaseOrder/ns0:PartnerName%-%XPATH=//ns0:PurchaseOrder/ns0:ID%|PurchaseOrder – Contoso-10001|  
  
## <a name="supported-macros"></a>支持的宏  
  
|设计时值|运行时值|  
|-----------------------|-------------------|  
|%MessageID%|BizTalk 消息 ID，该 ID 是唯一的 GUID。|  
|%SendingOrchestrationID%|作为消息起源的业务流程实例的 BizTalk ID。|  
|%SendingOrchestrationType%|作为消息起源的业务流程的类型名称。|  
|%Xpath =\<xpath\>%|允许指定一个 XPATH，用于从消息中提取值。 "\<xpath\>"必须替换为有效的 XPATH 表达式。 **注意：**必须中的 Namespace 别名或 WSS 的表达式的外部定义的命名空间别名。ConfigNamespaceAliases 字段。|  
|%Filename%|替换为从消息上下文属性 WSS.Filename 中提取的文件名值。 从 SharePoint 接收的消息已将 WSS.Filename 上下文属性值设置为 SharePoint 文件的名称。 使用 Path.GetFilenameWithoutExtension 对返回值进行预处理。 **注意：**中 WSS 不能使用此宏。配置 * （从业务流程） 的上下文属性。|  
|%Extension%|替换为从消息上下文属性 WSS.Filename 中提取的文件扩展名值。 从 SharePoint 接收的消息已将 WSS.Filename 上下文属性值设置为 SharePoint 文件的名称。 使用 Path.GetExtension 对返回值进行预处理。 返回值将不会包含“.”。 **注意：**中 WSS 不能使用此宏。配置 * （从业务流程） 的上下文属性。|  
  
 属性升级所支持的任何有效的表达式都是有效的设计时文件名。 设计时文件名将在运行时扩展为 Windows SharePoint Services 文件名。 此 Windows SharePoint Services 文件名具有某些其他限制，如下所述：  
  
-   有效的 Windows 文件名称可以包含除以下外的任何 Unicode 字符: / \: *？  /< &#124; "# {} %& ~ 或选项卡上字符和多个段。  
  
-   文件名的长度不得超过 256 个字符，整个 URL 的长度必须小于或等于 256 个字符。  
  
-   如果扩展的 Windows SharePoint Services 文件名包含无效字符，或扩展的文件名或 URL 太长，则将在应用程序事件日志中记录错误，并挂起该消息。 在使用消息事件和服务实例跟踪时，您还可以在“组中心”页中查看该错误和消息状态。  
  
## <a name="see-also"></a>另请参阅  
 [如何配置 Windows SharePoint Services 接收位置](../core/how-to-configure-a-windows-sharepoint-services-receive-location.md)   
 [如何配置 Windows SharePoint Services 发送处理程序](../core/how-to-configure-a-windows-sharepoint-services-send-handler.md)   
 [如何配置 Windows SharePoint Services 发送端口](../core/how-to-configure-a-windows-sharepoint-services-send-port.md)   
 [Windows SharePoint Services 适配器属性参考](../core/windows-sharepoint-services-adapter-properties-reference.md)   
 [支持的 Windows SharePoint Services 栏类型](../core/supported-windows-sharepoint-services-column-types.md)