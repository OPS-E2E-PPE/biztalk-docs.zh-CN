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
ms.openlocfilehash: 41b66ae9dd0149e8172726ff882de11dcf35ba25
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65528591"
---
# <a name="arbitrary-xpath-property-handler-biztalk-server-sample"></a>任意 XPath 属性处理程序 （BizTalk Server 示例）
任意 XPath 属性处理程序 ([!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]示例) 演示如何编写自定义管道组件以升级提交到的 XML 文档的特定属性[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 此示例中包含的功能可用于创建自定义的常规、 组装器和拆装器组件，以计算 XPath 表达式。  
  
## <a name="what-this-sample-does"></a>本示例的用途  
 该示例包括处理，DocInstance.xml 的采购订单 (PO) XML 文档。 此示例使用以下步骤处理 DocInstance.xml:  
  
1. 检索 DocInstance.xml[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]接收端口和由任意 XPath 属性处理程序调用的自定义管道组件。  
  
2. 任意 XPath 属性处理程序组件将升级所有\<价格\>并\<Quantity\>采购订单架构中定义为任意 XPath 表达式的元素。 XPath 表达式还包含与 PO 文档根元素的不明确的子元素一起使用的位置构造。  
  
3. 任意 XPath 属性处理程序组件确定消息类型，并将其升级到消息上下文。  
  
4. 然后，组件将具有已升级元素的 XML 文档发送到业务流程以便进一步处理。  
  
5. 业务流程访问 PO 文档中的已升级的元素并计算 PO 中项的总数。  
  
6. 业务流程将创建包含原始采购订单和更新的总数中信息的新采购订单文档。  
  
7. 新 PO 文档写入 \Output 目录中的文件。  
  
## <a name="where-to-find-this-sample"></a>本示例所在的位置  
 *\<Samples Path\>* \Pipelines\ArbitraryXPathPropertyHandler  
  
 下表显示了本示例中的文件及其用途说明：  
  
|文件|Description|  
|---------------|-----------------|  
|ArbitraryXPathPropertyHandler.sln|自定义管道组件解决方案文件。|  
|ArbitraryXPathPropertyHandler.resX|资源文件。|  
|ArbitraryXPathPropertyHandlerComp.cs|主要组件实现。|  
|AssemblyInfo.cs|程序集信息。|  
|Cleanup.bat|示例清理文件。|  
|PromotingMap.cs|属性升级为本机 CLR 类型的映射实现。|  
|PropertyAttributes.cs|自定义特性、 属性说明符和 ICustomTypePropertyDescriptor 实现。|  
|SchemaMap.cs|从消息类型到 IDocumentSpec 若要解决架构不明确问题架构映射。|  
|Setup.bat|生成和安装示例管道组件。|  
|VirtualStream.cs|虚拟流实现。|  
|SeekableReadOnlyStream.cs|可查找只读流实现。|  
|ArbitraryXPathSample.sln|示例业务流程解决方案文件。|  
|CalculateTotalAmount.odx|示例业务流程。|  
|PODocument.xsd|采购订单架构。|  
|DocInstance.xml|示例采购订单实例。|  
  
## <a name="building-and-initializing-this-sample"></a>生成并初始化此示例  
 此示例设计为在运行[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]具有环境[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]在同一台计算机上运行。 如果你的环境与此配置不匹配，则必须修改任意 XPath 属性处理程序 ([!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]示例) 以指向正确的 SQL Server 计算机。  
  
> [!IMPORTANT]
>  Setup.bat 假定 Microsoft Windows 安装目录为 C:\Windows。 如果您的 Windows 安装在另一个目录，必须修改 ArbitraryXPathPropertyHandler.csproj 文件以反映 Microsoft.BizTalk.Component.Utilities 程序集在全局程序集缓存中的位置。 在引用元素中，更改\<SYSTEMROOT\>到 Windows 的安装位置 (例如，C:\WINNT\\)。  
  
```  
<Reference  
  Name = "Microsoft.BizTalk.Component.Utilities"  
  AssemblyName = "Microsoft.BizTalk.Component.Utilities"  
  HintPath = "<SYSTEMROOT>\assembly\GAC\Microsoft.BizTalk.Component.Utilities\3.0.1.0__31bf3856ad364e35\Microsoft.BizTalk.Component.Utilities.dll"  
/>  
```  
  
 使用以下过程生成并初始化任意 XPath 属性处理程序 ([!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]示例)。  
  
#### <a name="to-build-and-initialize-this-sample"></a>若要生成并初始化本示例  
  
1. 在命令窗口中，将目录更改 (**cd**) 的以下文件夹：  
  
    *\<Samples Path\>* \Pipelines\ArbitraryXPathPropertyHandler  
  
2. 运行文件 Setup.bat，以执行以下操作：  
  
   - 生成任意 XPath 属性处理程序管道组件。  
  
   - 要为其生成的副本管道组件*\<安装路径\>* \Pipeline Components 目录。  
  
   - 创建发送端口和接收端口。  
  
   - 创建示例中使用的输入和输出目录。  
  
   - 将此示例安装[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]业务流程 ArbitraryXPathSample。  
  
   - 将端口绑定到示例业务流程。  
  
   - 启动业务流程。  
  
   > [!NOTE]
   >  应在生成和初始化过程中不报告任何错误。 如果出现任何错误，请确保已安装的所有必需软件，并且 Microsoft 生成工具的路径上可用。  
   > 
   > [!NOTE]
   >  若要撤消 Setup.bat 所做的更改，必须先停止并重新启动主机实例从[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。 接下来，运行 Cleanup.bat。 必须运行 Setup.bat 前运行 Cleanup.bat 时间。  
  
## <a name="running-this-sample"></a>运行本示例  
 使用以下过程运行任意 XPath 属性处理程序 ([!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]示例)。  
  
#### <a name="to-run-this-sample"></a>运行本示例的步骤  
  
1.  将采购订单 (PO) 文件 DocInstance.xml 复制到 \Input 目录。 PO 文件是将 XML 数据发送到任意 XPath 属性处理程序管道组件的接收端口提取。  
  
2.  查看 \Output 目录中的内容。 请注意，新的文件创建包含复制到 \Input 目录的 DocInstance.xml 文件的所有信息。 在文件中的区别在于现在\<TotalAmount\>元素填入采购订单的总金额。  
  
## <a name="comments"></a>注释  
 规范化 XPath 表达式是简单表达式，如"/ * [local-name = 元素的 name and =http://MyUri.org] /\*[本地名称 （) = 元素的 name] / @\*[本地名称 = attribute name]"。  
  
 任意 XPath 表达式可以是很复杂，比如"//element-name//* [本地名称 （) = 元素名称和位置 （） = 2]"。 如果这一事实，您将收到一个运行时错误，指出，不受非规范化 XPath 表达式[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]如果架构的 XPath 正文或某个 XPath 属性中使用了非规范化 XPath。 若要支持任意 XPath 表达式的解决方案是创建支持任意 XPath 正文和任意 XPath 属性表达式的自定义拆装器和组装器组件。  
  
 此示例使用以下步骤序列中的自定义管道组件时**IComponent.Execute**实现：  
  
1.  通过输入的消息正文部分流创建虚拟可查找的流。 （因为输入的消息可能很大，流不可查找，它应具有较小的内存需求量并且能够更改流位置。）  
  
2.  为其创建新的传出消息和新的正文部分、 将虚拟流分配给新正文部分，克隆正文部分属性和克隆消息上下文。  
  
3.  获取输入的消息或在设计时指定的基于的架构的架构。  
  
4.  将流加载到的实例**System.Xml.XmlDocument**。  
  
5.  将引导完成升级的属性和可分辨的字段和升级或将其写入到传出消息的消息上下文。  
  
6.  返回传出消息。  
  
7.  向文件写入传出消息。  
  
## <a name="see-also"></a>请参阅  
 [管道 （BizTalk Server 示例文件夹中）](../core/pipelines-biztalk-server-samples-folder.md)