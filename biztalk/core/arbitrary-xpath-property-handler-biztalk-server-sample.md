---
title: 任意 XPath 属性处理程序 （BizTalk Server 示例） |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pipeline components [custom], examples
- examples, pipeline components [custom]
ms.assetid: 4eb26c38-5ece-42b0-a28e-73214df1dc41
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 91cac57a7651e0ab0abaebe3de42f89e5f49179e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36977278"
---
# <a name="arbitrary-xpath-property-handler-biztalk-server-sample"></a>任意 XPath 属性处理程序 （BizTalk Server 示例）
任意 XPath 属性处理程序（[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 示例）演示了如何编写自定义管道组件以升级提交到 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 的 XML 文档中的特定属性。 您可以使用示例中包含的功能创建自定义常规组装器和拆装器组件以评估 XPath 表达式。  
  
## <a name="what-this-sample-does"></a>本示例的用途  
 本示例包括要处理的采购订单 (PO) XML 文档 DocInstance.xml。 本示例将使用以下步骤处理 DocInstance.xml：  
  
1. DocInstance.xml 由 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 接收端口检索并由称为“任意 XPath 属性处理程序”的自定义管道组件进行处理。  
  
2. 任意 XPath 属性处理程序组件将升级所有\<价格\>并\<Quantity\>采购订单架构中定义为任意 XPath 表达式的元素。 XPath 表达式还包含与 PO 文档根元素的不明确的子元素一起使用的位置构造。  
  
3. 任意 XPath 属性处理程序组件可确定消息类型并将其升级到消息上下文中。  
  
4. 然后，该组件将具有已升级元素的 XML 文档发送到业务流程以便进一步处理。  
  
5. 该业务流程将访问 PO 文档中的已升级元素并计算 PO 中项的总数。  
  
6. 该业务流程将创建包含原始 PO 中的信息及已更新总数的新 PO 文档。  
  
7. 新 PO 文档将写入 \Output 目录中的文件。  
  
## <a name="where-to-find-this-sample"></a>本示例所在的位置  
 *\<示例路径\>* \Pipelines\ArbitraryXPathPropertyHandler  
  
 下表显示了本示例中的文件及其用途说明：  
  
|文件|Description|  
|---------------|-----------------|  
|ArbitraryXPathPropertyHandler.sln|自定义管道组件解决方案文件。|  
|ArbitraryXPathPropertyHandler.resX|资源文件。|  
|ArbitraryXPathPropertyHandlerComp.cs|主要组件实现。|  
|AssemblyInfo.cs|程序集信息。|  
|Cleanup.bat|示例清理文件。|  
|PromotingMap.cs|属性升级为本机 CLR 类型的映射实现。|  
|PropertyAttributes.cs|自定义属性、属性说明符和 ICustomTypePropertyDescriptor 实现。|  
|SchemaMap.cs|从消息类型映射到 IDocumentSpec 的架构，用于解决架构不明确问题。|  
|Setup.bat|生成和安装示例管道组件。|  
|VirtualStream.cs|虚拟流实现。|  
|SeekableReadOnlyStream.cs|可查找的只读流实现。|  
|ArbitraryXPathSample.sln|示例业务流程解决方案文件。|  
|CalculateTotalAmount.odx|示例业务流程。|  
|PODocument.xsd|采购订单架构。|  
|DocInstance.xml|示例采购订单实例。|  
  
## <a name="building-and-initializing-this-sample"></a>生成并初始化本示例  
 本示例设计为在同一台计算机上运行有 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 的 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] 环境中运行。 如果您的环境与此配置不匹配，则您必须修改任意 XPath 属性处理程序（[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 示例）以指向 SQL Server 计算机。  
  
> [!IMPORTANT]
>  Setup.bat 假定 Microsoft Windows 安装目录为 C:\Windows。 如果 Windows 安装在其他目录中，则必须修改 ArbitraryXPathPropertyHandler.csproj 文件以反映 Microsoft.BizTalk.Component.Utilities 程序集在全局程序集缓存中的位置。 在引用元素中，更改\<SYSTEMROOT\>到 Windows 的安装位置 (例如，C:\WINNT\\)。  
  
```  
<Reference  
  Name = "Microsoft.BizTalk.Component.Utilities"  
  AssemblyName = "Microsoft.BizTalk.Component.Utilities"  
  HintPath = "<SYSTEMROOT>\assembly\GAC\Microsoft.BizTalk.Component.Utilities\3.0.1.0__31bf3856ad364e35\Microsoft.BizTalk.Component.Utilities.dll"  
/>  
```  
  
 使用以下过程生成并初始化任意 XPath 属性处理程序（[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 示例）。  
  
#### <a name="to-build-and-initialize-this-sample"></a>构建和初始化此示例  
  
1. 在命令窗口中，将目录更改 (**cd**) 的以下文件夹：  
  
    *\<示例路径\>* \Pipelines\ArbitraryXPathPropertyHandler  
  
2. 运行 Setup.bat 文件，该文件将执行以下操作：  
  
   - 生成任意 XPath 属性处理程序管道组件。  
  
   - 要为其生成的副本管道组件*\<安装路径\>* \Pipeline Components 目录。  
  
   - 创建发送端口和接收端口。  
  
   - 创建示例中使用的输入和输出目录。  
  
   - 安装示例 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 业务流程 ArbitraryXPathSample。  
  
   - 将端口绑定到示例业务流程。  
  
   - 启动业务流程。  
  
   > [!NOTE]
   >  在生成和初始化期间不应报告任何错误。 如果出现任何错误，请确保安装了所有所需软件并且路径中的 Microsoft 生成工具可用。  
   > 
   > [!NOTE]
   >  若要撤消 Setup.bat 所做的更改，必须首先从 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台停止并重新启动主机实例。 然后运行 Cleanup.bat。 必须运行 Setup.bat 前运行 Cleanup.bat 时间。  
  
## <a name="running-this-sample"></a>运行本示例  
 使用以下过程运行任意 XPath 属性处理程序（[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 示例）。  
  
#### <a name="to-run-this-sample"></a>运行本示例的步骤  
  
1.  将采购订单 (PO) 文件 DocInstance.xml 复制到 \Input 目录。 接收端口提取该 PO 文件，并将 XML 数据发送到任意 XPath 属性处理程序管道组件。  
  
2.  查看 \Output 目录中的内容。 请注意，创建了一个新文件，它包含复制到 \Input 目录的 DocInstance.xml 文件的所有信息。 在文件中的区别在于现在\<TotalAmount\>元素填入采购订单的总金额。  
  
## <a name="comments"></a>注释  
 规范化 XPath 表达式是简单表达式，如"/ * [local-name = 元素的 name and =http://MyUri.org] /\*[本地名称 （) = 元素的 name] / @\*[本地名称 = attribute name]"。  
  
 任意 XPath 表达式是复杂表达式，例如“//element-name//*[local-name()='element-name' and position()=2]”。 事实上，如果架构的 XPath 正文或某个 XPath 属性中使用了非规范化 XPath，则您将收到一个运行时错误，指出 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 不支持非规范化 XPath 表达式。 支持任意 XPath 表达式的解决方案是，创建支持任意 XPath 正文和任意 XPath 属性表达式的自定义拆装器和组装器组件。  
  
 此示例使用以下步骤序列中的自定义管道组件时**IComponent.Execute**实现：  
  
1.  通过输入消息正文部分流创建虚拟可查找的流。 （因为输入消息可能较大并且该流可能不可查找，它应具有较小的内存需求量并且能够更改流位置。）  
  
2.  为输入消息创建一个新的传出消息和新的正文部分，将虚拟流分配给新正文部分，克隆正文部分属性，然后克隆消息上下文。  
  
3.  为输入消息获取一个架构或基于设计时指定的架构。  
  
4.  将流加载到的实例**System.Xml.XmlDocument**。  
  
5.  演练升级属性和可分辨字段并将其升级到或写入传出消息的消息上下文。  
  
6.  返回传出消息。  
  
7.  将传出消息写入文件。  
  
## <a name="see-also"></a>请参阅  
 [管道（BizTalk Server 示例文件夹）](../core/pipelines-biztalk-server-samples-folder.md)