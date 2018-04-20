---
title: 如何配置发送端口使用 Windows Sharepoint Services 上下文属性 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Windows SharePoint Services adapters, InfoPath forms
- configuring [Windows SharePoint Services adapters], InfoPath forms
- Windows SharePoint Services adapters, Windows SharePoint Services
- InfoPath forms, Windows SharePoint Services adapters
- configuring [Windows SharePoint Services adapters], Windows SharePoint Services
- Windows SharePoint Services adapters, send ports
- configuring [Windows SharePoint Services adapters], send ports
- send ports, Windows SharePoint Services adapters
- Windows SharePoint Services, Windows SharePoint Services adapters
ms.assetid: 1ff50fb8-7ba0-47b8-9476-d57413989346
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e766272f33bf23166ba412a76498e4240ab3343b
ms.sourcegitcommit: 36350889f318e1f7e0ac9506dc8df794d475bda6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/20/2018
---
# <a name="how-to-configure-send-ports-using-windows-sharepoint-services-context-properties"></a>如何配置发送端口使用 Windows Sharepoint Services 上下文属性
本主题介绍如何使用 BizTalk 业务流程中的 Windows SharePoint Services 上下文属性在运行时配置 Windows Sharepoint Services 发送端口。 这一机制还可用于配置 Windows SharePoint Services 动态和后期绑定发送端口。 动态发送端口的配置属性是在运行时通过业务流程设置的。 适配器属性中公开 **Windows SharePoint Services 传输属性** 对话框还可应用于动态或后期绑定的发送端口。 若要使用 Windows Sharepoint Services 适配器上下文属性为动态或后期绑定发送端口设置配置属性，请执行以下步骤：  
  
### <a name="to-set-configuration-properties-for-a-send-port-using-windows-sharepoint-services-adapter-context-properties"></a>使用 Windows Sharepoint Services 适配器上下文属性为发送端口设置配置属性  
  
1.  对于动态发送端口，要创建动态单向发送端口，请按照主题中的步骤[如何创建发送端口](../core/how-to-create-a-send-port2.md)。  
  
2.  使用 **消息分配** 中调整 **构造消息** 形状中业务流程以设置配置属性的出站消息。 有关如何设置出站消息的配置属性的示例，请参阅[演练： 模块 3-从业务流程访问 SharePoint 属性](../core/walkthrough-module-3-accessing-sharepoint-properties-from-an-orchestration.md)。 **构造一条新消息** 本主题的部分演示如何设置配置的出站消息的属性。 可以在中设置的属性关联的适配器上下文属性 **Windows SharePoint Services 传输属性** 下表中列出对话框中︰  
  
    |传输属性|适配器上下文属性|数据类型|注释|  
    |------------------------|------------------------------|---------------|--------------|  
    |适配器 Web Services 端口|WSS.ConfigAdapterWSPort|int|有效值为从 1 到 65535。<br /><br /> 默认值为 80|  
    |超时|WSS.ConfigTimeout|int|有效值为从 1000年到 2147483647 之间<br /><br /> 默认值为 100000<br /><br /> 指定值 0 表示无限超时。|  
    |目标文件夹 URL|不适用|不适用|为使用动态端口，这设置间接的设置 **Microsoft.XLANGs.BaseTypes.Address** 属性具有表达式形状中业务流程的动态端口。 对于后期绑定端口，由于此属性始终被物理发送端口值覆盖，因此无法在运行时设置。|  
    |Filename|WSS.Filename|字符串|支持除之外的传输属性中的所有可用的文件名宏使用 **%filename%** 和 **%扩展 %** 宏。|  
    |命名空间别名|WSS.ConfigNamespaceAliases|字符串|如果在运行时为消息设置的命名空间别名与为消息路由到的发送端口设置的命名空间别名完全匹配，则这些命名空间将合并，并且会发生路由错误。 若要避免此问题，请确保指定的命名空间别名不相同。 例如，如果在业务流程中使用以下表达式来设置消息的命名空间别名：<br /><br /> `Message_Task(WSS.ConfigNamespaceAliases)= "orchns='http://OrderProcess.PurchaseOrder'";`<br /><br /> 如果此消息路由到指定的以下值发送端口和 **Namespace 别名** 属性︰<br /><br /> orchns =http://OrderProcess.PurchaseOrder<br /><br /> 那么当 BizTalk Server 尝试将消息路由到此发送端口时便会发生错误。 要解决此问题可以指定以下值以查找 **Namespace 别名** 发送端口的属性︰<br /><br /> **orchns2**=http://OrderProcess.PurchaseOrder|  
    |Overwrite|WSS.ConfigOverwrite|字符串|有效值包括：<br /><br /> -"是"<br /><br /> -"否"<br /><br /> -"重命名"|  
    |SharePoint 站点 URL|WSS.InListUrl|字符串|为使用动态端口，这设置间接的设置 **Microsoft.XLANGs.BaseTypes.Address** 属性具有表达式形状中业务流程的动态端口。 对于后期绑定端口，由于此属性始终被物理发送端口值覆盖，因此无法在运行时设置。|  
    |Microsoft Office 集成|WSS.ConfigOfficeIntegration|字符串|有效值包括：<br /><br /> -"是"<br /><br /> -"否"<br /><br /> -"yesformlibrary"<br /><br /> -"可选"|  
    |模板文档库|WSS.ConfigTemplatesDocLib|字符串|无|  
    |模板后备文档库|WSS.ConfigCustomTemplatesDocLib|字符串|InclusionThresholdSetting|  
    |模板后备命名空间栏|WSS.ConfigCustomTemplatesNamespaceCol|字符串|无|  
    |模板命名空间栏|WSS.ConfigTemplatesNamespaceCol|字符串|无|  
    |列 `n`|WSS.ConfigPropertiesXml<br /><br /> 在中设置列名称\<PropertyName*x*\>*columnname*\</ PropertyName*x* \>字段。|字符串|无|  
    |列 `n` 值|WSS.ConfigPropertiesXml<br /><br /> 在中设置列值\<PropertySource*x*\>*columnvalue*\</ PropertySource*x* \>字段。|字符串|支持除之外的传输属性中的所有可用的文件名宏使用 **%filename%** 和 **%扩展 %** 宏。|  
  
    > [!NOTE]
    >  为上下文属性提供的值都是区分大小写的。 在使用上下文属性设置动态端口的配置值时，需确保使用正确的大小写格式，否则，如果 BizTalk 尝试将文档路由到指定的发送端口，将会出现错误。  
  
3.  使用表达式形状中业务流程将 **Microsoft.XLANGs.BaseTypes.Address** 属性动态发送端口。 此属性用于指定动态发送端口将消息路由到的 URI。 有关如何设置的示例**Microsoft.XLANGs.BaseTypes.Address**动态发送端口属性请参阅**创建一个表达式**主题的部分[演练： 模块 3-从业务流程访问 SharePoint 属性](../core/walkthrough-module-3-accessing-sharepoint-properties-from-an-orchestration.md)。 有关 Windows Sharepoint Services 适配器上下文属性的详细信息请参阅[Windows SharePoint Services 适配器属性参考](../core/windows-sharepoint-services-adapter-properties-reference.md)。  
  
     另外，也可以在业务流程中动态设置后期绑定 Windows Sharepoint Services 发送端口的某些属性。 这样，Windows SharePoint Services 端口将配置两次，一次是通过 Windows SharePoint Services 上下文属性，一次是通过“Windows SharePoint Services 传输属性”对话框。 默认情况下，在“Windows SharePoint Services 传输属性”对话框中指定的配置优先于在上下文属性中指定的配置属性。 若要使用在上下文属性中指定的配置，请执行以下操作：  
  
    1.  若要创建一个静态单向发送端口，请按照本主题中的步骤[如何创建发送端口](../core/how-to-create-a-send-port2.md)。  
  
    2.  设置为发送端口属性时，通过输入适当的值的定义发送端口的 URI **Sharepoint 站点 URL** 和 **目标文件夹 URL** 属性。  
  
    3.  设置的值 **覆盖** 属性 **Orchestration** 如果想要使用的上下文属性所定义的值 **WSS。ConfigOverwrite** 业务流程中。  
  
    4.  设置 **Microsoft Office 集成** 属性 **Orchestration** 如果想要使用的上下文属性所定义的值 **WSS。ConfigOfficeIntegration** 业务流程中。  
  
    5.  输入的值为 **-1** 为任何发送端口属性使用整数数据类型，如果你想要在业务流程中设置的上下文属性为这些值。  
  
    6.  对于使用字符串数据类型的任何发送端口属性，若要使用业务流程中的上下文属性设置它们的值，请将其留空。 这不适用于 **Sharepoint 站点 URL** 和 **目标文件夹 URL** 属性。 必须将这些属性指定在 **Windows Sharepoint Services 传输属性** 对话框。  
  
    7.  使用 **消息分配** 中调整 **构造消息** 形状中业务流程以设置配置属性的出站消息。 有关如何设置出站消息的配置属性的示例，请参阅[演练： 模块 3-从业务流程访问 SharePoint 属性](../core/walkthrough-module-3-accessing-sharepoint-properties-from-an-orchestration.md)。 **构造一条新消息** 本主题的部分演示如何设置配置的出站消息的属性。  
  
    8.  值配置为 -1（使用整数数据类型的属性）、“业务流程”（下拉枚举属性）或留空（使用字符串数据类型的属性）的任何发送端口属性都将在运行时使用业务流程中指定的上下文属性进行设置。  
  
 如果你使用 Windows SharePoint Services 适配器接收带有嵌入的附件的 InfoPath 窗体，然后将 InfoPath 窗体发送到 SharePoint 文档库，完成以下步骤以保留该窗体中任何 InfoPath 处理指令︰  
  
### <a name="to-preserve-infopath-processing-instructions-for-infopath-forms-with-embedded-attachments-processed-by-biztalk-server"></a>为具有 BizTalk Server 处理的嵌入附件的 InfoPath 表单保留 InfoPath 处理指令  
  
1.  如果你使用地图中业务流程进行映射数据从一个 InfoPath 窗体复制到另一个的 InfoPath 窗体，确保已将 **复制处理指令 (Pi)** 中映射到属性 **是**。 此参数设置下 **自定义标头** 部分 **网格属性** 地图的页。  
  
2.  如果使用的不是业务流程中的映射，请在消息赋值形状中使用以下表达式来更新输出消息：  
  
    ```  
    NewMessage(XMLNORM.ProcessingInstructionOption) = 1;  
    NewMessage(XMLNORM.ProcessingInstruction) = "<?mso-infoPath-file-attachment-present?>"  
    ```  
  
     在更高版本，表达式中 *NewMessage* 是要添加到处理指令的输出消息。  
  
## <a name="see-also"></a>另请参阅  
 [如何创建发送端口](../core/how-to-create-a-send-port2.md)