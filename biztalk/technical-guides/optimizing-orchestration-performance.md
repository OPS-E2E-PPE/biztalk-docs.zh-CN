---
title: 优化业务流程性能 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 437c7325-f037-451a-8dbd-f8d8c8889e20
caps.latest.revision: 25
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 688aae3d543d93941bb356c0d6d207eb1d4be851
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65291412"
---
# <a name="optimizing-orchestration-performance"></a>优化业务流程性能
本主题介绍在 BizTalk Server 解决方案中使用业务流程的最佳实践。 这包括有关建议：  
  
-   减少使用业务流程的 BizTalk Server 解决方案的延迟  
  
    -   消除消息传送模式仅用于业务流程  
  
    -   利用内联从业务流程将发送  
  
    -   最大程度减少业务流程持久化点  
  
-   嵌套业务流程  
  
-   业务流程设计模式  
  
-   业务流程的异常处理块  
  
## <a name="recommendations-for-optimizing-orchestrations-for-low-latency-scenarios"></a>有关优化的低延迟方案的业务流程的建议  
 可以使用以下方法以减少使用业务流程的 BizTalk Server 解决方案的延迟。  
  
### <a name="eliminate-orchestrations-for-messaging-only-patterns"></a>消除消息传送模式仅用于业务流程  
 尽可能最小化使用业务流程来提高总体吞吐量并减少的业务流程的延迟。 如果存在无需运行长时间运行的事务，并且无需调用为每个请求的多个系统，请考虑消除业务流程和将业务逻辑移到接收和发送端口，以减少往返的总金额BizTalkMsgBoxDb 和减少延迟，因为数据库访问权限。 在这种情况下，实现自定义管道和重复使用以前已从业务流程调用的帮助程序类。 使用业务流程仅在万不得已时实现设计模式的散点图和收集或保护。 有关业务流程设计模式的详细信息，请参阅主题[业务流程中实现设计模式](http://go.microsoft.com/fwlink/?LinkId=140042)(http://go.microsoft.com/fwlink/?LinkId=140042) BizTalk Server 文档中。  
  
### <a name="use-inline-sends-from-orchestrations-to-accommodate-low-latency-scenarios"></a>使用内联形式从发送业务流程以适应较低的延迟情况  
 只要有可能，尽量减少使用的业务流程，并倾向于仅消息传递模式来提高总体吞吐量并减少的业务流程的延迟。 如果长时间运行的事务不需要且无需为业务逻辑来调用多个系统，然后考虑移动业务逻辑来接收和发送端口并消除使用业务流程。 这种方法可以实现包含自定义管道，并且其中重复使用以前已从业务流程调用的帮助程序类。 若要实现更好的性能低延迟方案，采用以下方法之一：  
  
-   消除不必要的业务流程，采用仅消息传递模式，以减少到 BizTalk MessageBox 数据库之间的往返次数的总金额。 这种方法可容纳较低的延迟，因为内联发送绕过 BizTalk 消息引擎和关联的开销。 业务流程内联发送功能提供 BizTalk Server 2006 和更高版本。  
  
-   在业务流程，消除逻辑端口绑定到物理端口，并使用在其位置的行中发送。 例如，内联发送无法用于创建 WCF 代理类来调用下游 Web 服务或 ADO.NET 组件来访问 SQL Server 数据库的实例。 在下图中，当业务流程实例化业务组件，可在内部使用 WCF 执行内联发送代理对象来直接调用下游 Web 服务：  
  
     ![BizTalk 业务流程内联发送的描述](../technical-guides/media/inlinesend.gif "InlineSend")  
  
> [!NOTE]
>  使用从业务流程内联发送将显著减少延迟，尽管存在一些限制到这种方法。 由于内联发送绕过 BizTalk 消息引擎，提供与消息引擎的以下功能不可用：  
> 
> - 事务性管道  
>   -   可恢复管道  
>   -   调用 BAM 侦听器 API 的管道  
>   -   BizTalk Server 适配器支持  
>   -   批处理  
>   -   重试次数  
>   -   相关集初始化  
>   -   声明性配置  
>   -   辅助传输  
>   -   跟踪  
>   -   BAM 的声明性使用  
  
 有关不能从业务流程中执行的管道的类型的详细信息，请参阅本主题的"限制"部分[如何使用表达式来执行管道](http://go.microsoft.com/fwlink/?LinkId=158008)(http://go.microsoft.com/fwlink/?LinkId=158008) BizTalk Server 中2010 的文档。  
  
### <a name="optimize-orchestration-latency-by-reducing-the-number-of-persistence-points-if-possible"></a>通过尽可能减少持久化点的数量来优化业务流程的延迟  
 业务流程作用域只需将其标记为"长时间运行的事务"如果你想要使用补偿或作用域超时。 长时间运行的事务作用域会导致末尾的作用域，一个额外的持久性点，因此它们不需要使用补偿或作用域超时时应避免使用。 原子作用域将导致暂留点末尾的范围，但还可确保不暂留点会在原子作用域内。 （执行多个发送时，例如），有时可以对你来说批处理持久化点使用该范围中没有持久性此副作用。 一般情况下，不过，我们建议尽量避免原子作用域。 业务流程引擎将保存到持久性存储区的不同位置，正在运行的业务流程实例的整个状态，以便实例更高版本可以还原在内存中并执行到完成。   
**在业务流程中的暂留点数目是影响源源不断地流经整个业务流程的消息的延迟的关键因素之一**。 引擎遇到持久点时，每次运行的业务流程的内部状态是序列化保存到 MessageBox 和此操作所产生的延迟开销。 序列化的内部状态包括的所有消息和实例化但尚未发布业务流程中的变量。 较大的消息和变量和其中的越多，就越长以保持业务流程的内部状态。 持久化点的次数过多可能会导致性能明显下降。 出于此原因，我们建议通过减少事务作用域的数量来消除不必要的持久化点从业务流程和发送形状。 此方法允许减少提高整体可伸缩性，并降低了业务流程延迟业务流程冻结和解除冻结，由于 MessageBox 上的争用现象。   
另一条建议是始终保持业务流程的内部状态越小越好。 此技术可以显著减少 XLANG 引擎序列化、 保存和还原业务流程持久化点时的内部状态所用的时间。 若要实现此目的的一种方法是尽可能创建变量和晚消息并发布它们尽早尽可能;例如引入了在您的业务流程内的非事务性作用域，并声明变量和这些内部作用域，而不是在最顶层级别声明它们中的消息。 最大程度减少业务流程持久化点的详细信息，请参阅 BizTalk Server 2010 文档中的以下主题：  
  
-   [持久化和业务流程引擎](http://go.microsoft.com/fwlink/?LinkID=155292)(http://go.microsoft.com/fwlink/?LinkID=155292)。  
  
-   [业务流程冻结和解除冻结](http://go.microsoft.com/fwlink/?LinkID=155284)(http://go.microsoft.com/fwlink/?LinkID=155292)。  
  
## <a name="guidelines-for-using-promoted-properties-to-access-message-tags-or-attributes-from-an-orchestration"></a>使用指南的已提升属性访问消息标记或属性从业务流程  
 如果您确实需要升级属性，将提升用于消息路由、 筛选器和消息关联的那些属性。 每个属性的升级要求的拆装器组件 （XML、 平面的自定义） 来确认文档类型以及从使用 XPath 表达式从相对的批注的 XSD 的文档类型定义中包含的消息中检索数据。 此外，每个属性升级会导致单独 bts_InsertProperty 存储过程的调用时消息代理将消息发布到 MessageBox 数据库。 如果业务流程需要访问的特定元素或特性所包含的 XML 文档，请使用以下方法之一：  
  
- 减少写入和升级的属性数目并消除那些不是必需的。  
  
- 消除不必要的可分辨的字段。 可分辨的字段将写入上下文属性，它们可轻松地会占用很多空间，如其名称等于用于检索数据的 XPath 表达式。 可分辨的属性定义为中定义的文档类型的 XSD 的批注。 拆装器组件使用相同的方法应用于升级的属性，并使用定义的可分辨的字段中查找传入文档中的 XPath 表达式。 然后，拆装器组件将属性写入上下文中其中：  
  
  - **名称**：在批注中定义的 XPath 表达式。  
  
  - “值”：通过传入文档中的 XPath 表达式标识的元素的值。  
  
    XPath 表达式可以是很长，尤其是当涉及的元素是非常深的文档架构中。 因此，更可分辨字段，可查看大上下文大小。 这进而产生负面影响的整体性能。  
  
- 使用业务流程运行时提供的内置 XPath 函数。  
  
- 如果消息非常小 （几个千字节为单位） 和 XML 格式，可以取消消息序列化为.NET 类实例，并使用公共字段和属性。 如果消息需要复杂的细化 （自定义代码、 业务规则引擎策略等） 使用.NET 类的实例公开的属性来访问数据将快得多，使用 XPath 表达式。 完成后调用的业务流程的业务逻辑，可以返回到 BizTalk 消息序列化实体对象。 可以从 XML 架构，使用以下工具之一创建.NET 类：XSD 工具 (.NET Framework 2.0) 或 SVCUTIL (.NET Framework 3.0)。  
  
- 启用从业务流程的帮助器组件。 此方法有其优点使用可分辨的字段。 实际上，业务流程可以读取的 XPath 表达式从配置存储 （配置文件、 SSO 配置存储区、 自定义 Db 等），因此时必须更改 XPath 表达式，无需更改和重新部署架构，你应为升级的属性和 distinguished 字段。 下面的代码示例提供帮助器组件的示例。 该组件使用 BizTalk 运行时提供的 XPathReader 类。 这使得代码可以读取整个文档流，直到找到 XPath 表达式。  
  
```  
#region Copyright  
//===  
//Microsoft Windows Server AppFabric Customer Advisory Team (CAT)   
//  
// This sample is supplemental to the technical guidance published on the community  
// blog.  
//   
// Author: Paolo Salvatori.  
//===  
// Copyright © 2010 Microsoft Corporation. All rights reserved.  
//   
// THIS CODE AND INFORMATION IS PROVIDED "AS IS" WITHOUT WARRANTY OF ANY KIND, EITHER   
// EXPRESSED OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE IMPLIED WARRANTIES OF   
// MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE. YOU BEAR THE RISK OF USING IT.  
//===  
#endregion  
#region Using Directives  
using System;  
using System.Collections.Generic;  
using System.IO;  
using System.Xml;  
using System.Linq;  
using System.Text;  
using System.Globalization;  
using Microsoft.XLANGs.BaseTypes;   
using Microsoft.BizTalk.Streaming;  
using Microsoft.BizTalk.XPath;  
#endregion  
namespace Microsoft.AppFabric.CAT.Samples.DuplexMEP.Helpers  
{  
public class XPathHelper  
{  
#region Private Constants   
private const string MessageCannotBeNull = "[XPathReader] The message cannot be null.";  
#endregion  
#region Public Static Methods  
public static string GetValue(XLANGMessage message, int partIndex, string xpath)  
{  
try  
{  
if (message == null)  
{  
throw new ApplicationException(MessageCannotBeNull);  
}  
using (Stream stream = message[partIndex].RetrieveAs(typeof(Stream)) as Stream)  
{  
XmlTextReader xmlTextReader = new XmlTextReader(stream);  
XPathCollection xPathCollection = new XPathCollection();  
XPathReader xPathReader = new XPathReader(xmlTextReader, xPathCollection);  
xPathCollection.Add(xpath);  
while (xPathReader.Read())  
{  
if (xPathReader.HasAttributes)  
{  
for (int i = 0; i < xPathReader.AttributeCount; i++)  
{  
xPathReader.MoveToAttribute(i);  
if (xPathReader.Match(xPathCollection[0]))  
{  
return xPathReader.GetAttribute(i);  
}  
}  
}  
if (xPathReader.Match(xPathCollection[0]))  
{  
return xPathReader.ReadString();  
}  
}  
}  
}  
finally  
{  
message.Dispose();  
}  
return string.Empty;  
}  
#endregion  
}  
}  
```  
  
## <a name="minimize-orchestration-complexity-to-improve-performance"></a>最小化业务流程的复杂性以提高性能  
 业务流程的复杂性对性能有重大影响。 随着业务流程的复杂性的增加，总体性能下降。 业务流程可以采用几近无限的各种方案，以及每个方案可能涉及的复杂程度各异的业务流程。 避免复杂的业务流程在可能的情况以支持模块化方法。 换而言之，将您的业务逻辑拆分为多个可重复使用的业务流程。  
  
 如果需要实现复杂的业务流程，定义消息和变量到内部作用域，只要有可能，而不是在根级别。 此方法会保持在内存中为每个业务流程更小空间，因为变量和消息时，将释放的流离开已定义的变量和消息的作用域。 如果业务流程将保存到 MessageBox 持久化点时，此方法非常尤为有益。  
  
## <a name="use-the-call-orchestration-shape-versus-the-start-orchestration-shape-to-improve-performance"></a>使用与启动业务流程形状调用业务流程形状可提高性能  
 避免**启动业务流程**形状，然后使用**调用业务流程**形状执行嵌套的业务流程。 事实上，**调用业务流程**形状可用于同步调用另一个项目中引用的业务流程。 此方法以供重复使用的常见业务流程工作流模式允许多个 BizTalk 项目。 调用以同步方式与另一个嵌套的业务流程时**调用业务流程**形状，封闭的业务流程将等待嵌套的业务流程完成后才能继续。 嵌套的业务流程调用业务流程运行在同一线程上执行。  
  
 **启动业务流程**形状是类似于**调用业务流程**形状，但在这种情况下以异步方式调用嵌套的业务流程： 中调用的控制流业务流程将继续调用，而无需等待调用的业务流程完成其工作。 为了实现之间调用方和被调用的业务流程，这种分离**启动业务流程**通过发布到 BizTalk Messagebox 的消息实现的。 然后，执行嵌套的业务流程的进程内 BizTalk 主机实例可使用此消息。 如果可能，请使用**调用业务流程**，特别是当调用业务流程需要等待才能继续处理从嵌套的业务流程的结果。  有关使用调用业务流程形状的详细信息，请参阅 BizTalk Server 2010 文档中的以下主题：  
  
-   [使用在业务流程直接绑定端口](http://go.microsoft.com/fwlink/?LinkId=139902)(http://go.microsoft.com/fwlink/?LinkId=139902)。  
  
-   [嵌套业务流程](http://go.microsoft.com/fwlink/?LinkId=139903)(http://go.microsoft.com/fwlink/?LinkId=139903)。  
  
## <a name="use-xmlreader-with-xlangmessage-versus-using-xmlreader-with-xmldocument-to-improve-orchestration-performance"></a>XmlReader 使用 XLANGMessage 与使用和 XmlDocument XmlReader 来提高业务流程性能  
 若要提高.NET 方法从业务流程调用的业务流程性能，请将 XmlReader 使用 XLANGMessage，不 XmlDocument。 下面的代码示例说明了此功能。  
  
```csharp  
// As a general rule, use XmlReader with XLANGMessage, not XmlDocument.   
// This is illustrated in the parameter passed into the following code.   
// The XLANG/s compiler doesn't allow a return value of XmlReader   
// so documents must be initially constructed as XmlDocument()  
public static XmlDocument FromMsg(XLANGMessage old)  
{  
    //get at the data  
    XmlDocument ret = new XmlDocument();  
  
    try{  
        XmlReader reader = (XmlReader)old[0].RetrieveAs(typeof(XmlReader));  
        //construct new message from old  
        //read property  
        object msgid = old.GetPropertyValue(typeof(BTS.MessageID));  
    }  
    finally {  
        // Call Dispose on the XLANGMessage object   
        // because the message doesn't belong to the   
        // .NET runtime - it belongs to the Messagebox database   
        old.Dispose();  
    }  
    return ret;  
}  
```  
  
 另一种方法就是创建基于架构的.NET 类。 这会占用较少内存比加载到文档**XmlDocument**对象，以及面向.NET 开发人员提供轻松访问的架构元素。 若要生成基于 BizTalk 架构的类，可以使用 xsd.exe 工具随 Visual Studio 一起提供。 例如，运行**xsd.exe \<schema.xsd\> /classes** ItemB，ItemC，将针对简单架构，其中包含名为 ItemA 的字段，生成下面的类。  
  
```csharp  
//------------------------------------------------------------------------------  
// <auto-generated>  
//     This code was generated by a tool.  
//     Runtime Version:2.0.50727.1433  
//  
//     Changes to this file may cause incorrect behavior and will be lost if  
//     the code is regenerated.  
// </auto-generated>  
//------------------------------------------------------------------------------  
  
using System.Xml.Serialization;  
  
//   
// This source code was auto-generated by xsd, Version=2.0.50727.42.  
//  
  
/// <remarks/>  
[System.CodeDom.Compiler.GeneratedCodeAttribute("xsd", "2.0.50727.42")]  
[System.SerializableAttribute()]  
[System.Diagnostics.DebuggerStepThroughAttribute()]  
[System.ComponentModel.DesignerCategoryAttribute("code")]  
[System.Xml.Serialization.XmlTypeAttribute(AnonymousType=true, Namespace="http://Schemas.MySchema")]  
[System.Xml.Serialization.XmlRootAttribute(Namespace="http://Schemas.MySchema", IsNullable=false)]  
public partial class MySchemaRoot {  
  
    private string itemAField;  
  
    private string itemBField;  
  
    private string itemCField;  
  
    /// <remarks/>  
    [System.Xml.Serialization.XmlElementAttribute(Form=System.Xml.Schema.XmlSchemaForm.Unqualified)]  
    public string ItemA {  
        get {  
            return this.itemAField;  
        }  
        set {  
            this.itemAField = value;  
        }  
    }  
  
    /// <remarks/>  
    [System.Xml.Serialization.XmlElementAttribute(Form=System.Xml.Schema.XmlSchemaForm.Unqualified)]  
    public string ItemB {  
        get {  
            return this.itemBField;  
        }  
        set {  
            this.itemBField = value;  
        }  
    }  
  
    /// <remarks/>  
    [System.Xml.Serialization.XmlElementAttribute(Form=System.Xml.Schema.XmlSchemaForm.Unqualified)]  
    public string ItemC {  
        get {  
            return this.itemCField;  
        }  
        set {  
            this.itemCField = value;  
        }  
    }  
}  
```  
  
 此类，可以引用.NET 程序集才能访问消息元素，并返回的对象可以直接分配到一条消息。 下面是类的上述生成的示例用法。  
  
```csharp  
public static Root SetValues(Microsoft.XLANGs.BaseTypes.XLANGMessage msg)  
{  
   try  
   {  
   MySchemaRoot rootObj=(MySchemaRoot)msg[0].RetrieveAs(typeof(MySchemaRoot);  
   rootObj.ItemA="value a";  
   rootObj.ItemB="value b";  
   rootObj.ItemC="value c";  
   }  
    finally {  
        msg.Dispose();  
            }  
  
   return rootObj;  
}  
```  
  
 此技术，可处理消息时使用的面向对象的方法。 此方法应主要用于相对较小的消息。 这是因为即使此方法使用少得多的内存比时加载到的消息**XmlDocument**对象，整个消息，仍将加载到内存。 在处理较大的消息时，使用**XmlReader**类，以读取消息并**XmlWriter**类将消息写入。 使用时**XmlReader**并**XmlWriter**，该消息包含在**为 VirtualStream**对象。 如果消息大小超出了为指定的值**大消息阈值 （字节）** 公开 BizTalk 组属性配置页上，将消息写入到文件系统。 这会降低整体性能，但可以避免内存不足异常。  
  
## <a name="improve-performance-by-minimizing-the-use-of-logical-ports-bound-to-physical-ports"></a>通过最小化的逻辑端口绑定到物理端口的使用来提高性能  
 可以通过尽量少使用的逻辑端口绑定到使用以下适配器的物理端口来提高性能：  
  
- SQL Server、 Oracle  
  
- WSE，HTTP，WCF  
  
- MSMQ, MQSeries  
  
  在 BizTalk Server 2010 中，发送和接收管道可以从业务流程使用 XLANGPipelineManager 类包含在 Microsoft.XLANGs.Pipeline.dll 直接调用。 因此，管道处理可以在端口间移动业务流程;具有表达式形状，调用给定的.NET 类的实例 （例如，使用 ADO.NET 数据访问组件），才能替代业务流程中的逻辑端口。 采用这种技术之前, 应注意，如果不使用适配器和物理端口，您会失去能够充分利用其函数，如批处理、 重试次数、 声明性配置和辅助传输。  
  
## <a name="orchestration-design-patterns"></a>业务流程设计模式  
 业务流程设计器允许开发人员实现范围广泛的企业集成模式。 一些常见模式包括聚合器、 异常处理和补偿、 消息中转站、 散点图和收集，并按顺序和并行保护。 可以利用这些模式开发复杂的企业应用程序集成 (EAI)、 面向服务体系结构 (SOA) 和业务流程管理 (BPM) 解决方案与 BizTalk Server。 有关业务流程设计模式的详细信息，请参阅主题[业务流程中实现设计模式](http://go.microsoft.com/fwlink/?LinkId=140042)(http://go.microsoft.com/fwlink/?LinkId=140042) BizTalk Server 文档中和[模式和最佳实践企业集成](http://go.microsoft.com/fwlink/?LinkId=140043)(http://go.microsoft.com/fwlink/?LinkId=140043)。  
  
## <a name="make-appropriate-use-of-net-classes-in-orchestrations-to-maximize-performance"></a>在业务流程来使性能最大化中进行适当使用.NET 类  
 一般情况下，在业务流程内部使用的.NET 类可以分为两个不同类别：  
  
-   **帮助程序和服务-** 这些类提供常见服务添加到业务流程，例如跟踪、 错误处理、 缓存和序列化/反序列化。 大多数这些类可以作为与没有内部状态和多个公共静态方法的静态类实现。 此方法可避免在不同的业务流程运行在同一时间，有助于减少主机进程的工作空间，并节省内存中创建的同一个类的多个对象。 无状态的类有助于减少必须序列化和业务流程会被冻结时保存到 BizTalk MessageBox 的内部状态的总体大小。  
  
-   **实体和业务对象-** 可以使用这些类来管理实体，例如订单、 订单项和客户。 单个业务流程可以在内部创建和管理多个相同类型的实例。 这些类通常有状态，并公开公共字段和/或属性及方法来修改该对象的内部状态。 这些类的实例可以动态创建的反 XLANGMessage 部分序列化为.NET 对象，通过使用**XmlSerializer**或**DataContractSerializer**类或通过使用**XLANGPart.RetrieveAs**方法。 您应构建业务流程使用有状态的类的实例的创建尽可能晚和不再需要后，即可释放方式中的非事务性作用域。 这种方法可以减少主机进程的工作空间并最小化的序列化并保存到 MessageBox 数据库中已冻结业务流程时的内部状态的总体大小。 有关 BizTalk Server 中使用业务流程的详细信息，请参阅文章[BizTalk Server 业务流程的常见问题解答](http://go.microsoft.com/fwlink/?LinkID=116886)(http://go.microsoft.com/fwlink/?LinkID=116886)。  
  
    > [!NOTE]  
    >  尽管这篇文章编写的 BizTalk Server 2004 和 BizTalk Server 2006 中，介绍的概念也适用于 BizTalk Server 2010 的业务流程。  
  
## <a name="orchestration-exception-handler-blocks"></a>业务流程的异常处理程序块  
 使用业务流程的异常处理程序块时，在一个或多个作用域 （非事务性作用域应尽可能） 中包含所有业务流程形状，并至少创建以下异常处理程序块：  
  
- 异常处理程序块用于处理一般的 System.Exception 错误。  
  
- 异常处理程序块用于处理常规异常以捕获和处理可能的非托管的错误，例如 COM 异常。  
  
  有关使用业务流程的异常处理块的详细信息，请参阅以下文章：  
  
- [使用 BizTalk Server 异常处理](http://msdn.microsoft.com/library/aa561229.aspx)(http://msdn.microsoft.com/library/aa561229.aspx)。  
  
- [Charles Young 博客，BizTalk Server 2006:补偿模型](http://go.microsoft.com/fwlink/?LinkId=158017)(http://go.microsoft.com/fwlink/?LinkId=158017)。  
  
  > [!NOTE]
  >  虽然此博客编写使用[!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)]的一点是，在博客中介绍的原则也适用于 BizTalk Server。  
  
## <a name="considerations-when-using-maps-in-orchestrations"></a>在业务流程中使用映射时的注意事项  
 在业务流程中使用映射时，应考虑以下事项：  
  
-   如果使用映射来提取或设置与一起使用的属性在业务流程中的业务逻辑使用可分辨的字段，或升级的属性。 应遵循这种做法，因为如果提取或设置文档的一个带有地图的值加载到内存但是时使用的可分辨字段或升级的属性，则业务流程引擎将访问消息上下文并不会加载到内存中的文档。  
  
-   如果您使用映射将多个字段聚合为一个字段，请使用可分辨的字段或升级的属性与业务流程变量累积的结果集。  
  
## <a name="see-also"></a>请参阅  
 [优化性能](../technical-guides/optimizing-performance.md)