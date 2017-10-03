---
title: "优化业务流程性能 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 437c7325-f037-451a-8dbd-f8d8c8889e20
caps.latest.revision: "25"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cbd45901afb229cf884390c2a5120deac0daa90d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="optimizing-orchestration-performance"></a>优化业务流程性能
本主题介绍在 BizTalk Server 解决方案中使用业务流程的最佳实践。 这包括有关建议：  
  
-   减少延迟的使用业务流程的 BizTalk Server 解决方案  
  
    -   消除消息仅模式的业务流程  
  
    -   利用内联发送从业务流程  
  
    -   最小化业务流程持久性点  
  
-   嵌套业务流程  
  
-   业务流程设计模式  
  
-   业务流程异常处理块  
  
## <a name="recommendations-for-optimizing-orchestrations-for-low-latency-scenarios"></a>有关优化为低延迟方案的业务流程的建议  
 可以使用以下方法以减少延迟的使用业务流程的 BizTalk Server 解决方案。  
  
### <a name="eliminate-orchestrations-for-messaging-only-patterns"></a>消除消息仅模式的业务流程  
 尽可能最小化使用业务流程来提高总体吞吐量并减少业务流程的延迟。 如果存在无需运行长时间运行事务，并且没有无需调用为每个请求的多个系统，请考虑消除业务流程和转向接收和发送端口，可以减少到往返总的业务逻辑BizTalkMsgBoxDb 和减少延迟，因为数据库访问。 在这种情况下，实现自定义管道，重复使用以前已从业务流程调用的帮助程序类。 使用仅在严格需要时的业务流程来实现的散点图和收集或保护的设计模式。 有关业务流程设计模式的详细信息，请参阅主题[实现在业务流程中的设计模式](http://go.microsoft.com/fwlink/?LinkId=140042)(http://go.microsoft.com/fwlink/?LinkId=140042) BizTalk Server 文档中。  
  
### <a name="use-inline-sends-from-orchestrations-to-accommodate-low-latency-scenarios"></a>使用内联支持业务流程的将发送以适应较低的延迟的情况  
 只要有可能，尽量少使用的业务流程和倾向于仅用于消息传送模式来提高总体吞吐量并减少业务流程的延迟。 如果无需为长时间运行事务，并且没有无需业务逻辑来调用多个系统，请考虑移动的业务逻辑来接收和发送端口和消除使用业务流程。 可以使用自定义管道实现这种方法，该重复使用以前已从业务流程调用的帮助器类。 为了实现更好的性能低延迟方案，采用以下方法之一：  
  
-   消除不必要的业务流程，并采用仅消息传送模式，以减少到 BizTalk MessageBox 数据库总之间的往返次数。 此方法还包含较低的延迟，因为内联发送绕过 BizTalk 消息传递引擎和关联的开销。 业务流程内联发送功能提供 BizTalk Server 2006 和更高版本。  
  
-   内部业务流程，消除了绑定到的物理端口的逻辑端口，并在行内使用发送在它们的位置。 例如，内联发送无法用于创建一个 WCF 代理类来调用下游 Web 服务或 ADO.NET 组件以访问 SQL Server 数据库的实例。 在下图中，当业务流程实例化在业务组件，可在内部使用 WCF 执行内联发送代理对象来直接调用下游 Web 服务：  
  
     ![BizTalk 业务流程内联发送描述](../technical-guides/media/inlinesend.gif "InlineSend")  
  
> [!NOTE]  
>  尽管使用内联发送从业务流程将显著减少延迟，有一些限制到这种方法。 由于内联发送绕过 BizTalk 消息引擎，请使用消息传递引擎提供的以下功能不可用：  
>   
>  -   事务性管道  
> -   可恢复管道  
> -   调用 BAM 拦截器 API 的管道  
> -   BizTalk Server 适配器支持  
> -   批处理  
> -   重试次数  
> -   相关集初始化  
> -   声明性配置  
> -   辅助传输  
> -   跟踪  
> -   声明方式使用 BAM  
  
 无法从内部业务流程执行的管道的类型的详细信息，请参阅主题的"限制"部分[如何使用表达式到执行管道](http://go.microsoft.com/fwlink/?LinkId=158008)(http://go.microsoft.com/fwlink/?LinkId = 158008) BizTalk Server 2010 文档中。  
  
### <a name="optimize-orchestration-latency-by-reducing-the-number-of-persistence-points-if-possible"></a>尽可能减少持久性点的数量，从而优化业务流程延迟  
 业务流程作用域仅需要标记为"长时间运行的事务"如果你想要使用补偿或作用域超时。 一个长时间运行的事务范围导致末尾的作用域，一个额外的持久性点，因此如果你不需要使用补偿或作用域超时，应避免它们。 原子作用域可使暂留点末尾的范围，但还可保证没有持久性点会在原子作用域内。 在范围内没有持久性此副作用有时可对你批处理持久性点用 （在执行多个发送，例如） 时。 通常情况下，不过，我们建议尽可能避免原子作用域。 业务流程引擎将保存到持久性存储区的各个点，在正在运行的业务流程实例的整个状态，以便实例更高版本可以还原在内存中并执行完成。   
**业务流程中的持久性点数目是影响消息流经业务流程的延迟的关键因素之一**。 引擎达到某个持久点时，每次并是此操作会产生延迟成本序列化正在运行业务流程内部状态并将其保存到 MessageBox。 序列化的内部状态包括所有消息以及实例化，但尚未发布业务流程中的变量。 更大的消息和变量和这些越多，将越长以保留的内部业务流程的状态。 过多的持久性点可能导致性能明显下降。 为此，我们建议通过减少事务的作用域数消除不必要的持久性点从业务流程，并发送形状。 此方法允许减少上提高总体可伸缩性，并降低了业务流程延迟由于业务流程冻结和 rehydration，MessageBox 的争用现象。   
另一个建议是始终保留的内部状态的业务流程越小越好。 这种技术可以显著减少 XLANG 引擎序列化、 保持及还原发生持久性点时的业务流程的内部状态所用的时间。 实现此目的的一种方法是尽可能创建变量和消息尽可能晚并释放这些尽早尽可能;例如引入了非事务性作用域内你的业务流程和声明变量和而不是在最顶层级别声明它们这些内部范围内的消息。 有关最小化业务流程持久性点的详细信息，请参阅 BizTalk Server 2010 文档中的以下主题：  
  
-   [持久性和业务流程引擎](http://go.microsoft.com/fwlink/?LinkID=155292)(http://go.microsoft.com/fwlink/?LinkID=155292)。  
  
-   [业务流程冻结和 Rehydration](http://go.microsoft.com/fwlink/?LinkID=155284) (http://go.microsoft.com/fwlink/?LinkID=155292)。  
  
## <a name="guidelines-for-using-promoted-properties-to-access-message-tags-or-attributes-from-an-orchestration"></a>使用的指导原则提升到访问消息标记或属性从业务流程的属性  
 如果你确实需要升级的属性，将提升用于消息路由、 筛选器，以及消息关联的那些属性。 在升级每个属性需要反汇编程序组件 （XML，平面，自定义） 来识别的文档类型，以及从使用从定义的文档类型的 XSD 中包含的相对批注的 XPath 表达式的消息中检索数据。 此外，每个属性提升在消息代理将消息发布到 MessageBox 数据库将导致 bts_InsertProperty 存储过程的一个单独的调用。 如果业务流程需要访问的特定元素或属性包含的 XML 文档，使用以下方法之一：  
  
-   减少写入和提升属性的数量并消除不需要严格。  
  
-   消除不必要的可分辨的字段。 可分辨的字段将写入上下文属性，它们可以轻松地占用大量的空间，因为其名称为等于可用于检索数据的 XPath 表达式。 可分辨的属性被定义为中定义的文档类型的 XSD 批注。 拆装器组件使用相同的方法采用的提升的属性，并使用定义的可分辨的字段，以查找在传入的文档中的 XPath 表达式。 然后，拆装器组件将属性写入的上下文中其中：  
  
    -   **名称**： 在批注中定义的 XPath 表达式。  
  
    -   **值**： 通过传入文档中的 XPath 表达式标识的元素的值。  
  
     尤其是在非常深的文档架构中所述元素时，则可能会很长，XPath 表达式。 因此，越区分字段，较大的上下文大小。 这反过来产生负面影响的整体性能。  
  
-   使用业务流程运行时提供的内置 XPath 函数。  
  
-   如果消息是相当微小 （几千字节为单位） 和 XML 格式，可以取消消息序列化为.NET 类实例，并使用公共字段和属性。 如果消息需要复杂的细化 （自定义代码、 业务规则引擎策略等） 使用.NET 类的实例公开的属性来访问数据是快得多，使用 XPath 表达式。 完成后调用的业务流程的业务逻辑，可以恢复到 BizTalk 消息序列化实体对象。 你可以从 XML 架构使用以下工具之一中创建.NET 类： XSD 工具 (.NET Framework 2.0) 或 SVCUTIL (.NET Framework 3.0)。  
  
-   启用业务流程的帮助程序组件。 此方法具有通过使用可分辨的字段优点。 事实上，业务流程可以读取的 XPath 表达式从配置存储 （配置文件、 SSO 配置存储区，自定义数据库等），因此你必须更改 XPath 表达式，则不需要更改和重新部署架构，当你在升级的属性和 d 的情况下应该执行操作istinguished 字段。 下面的代码示例提供了帮助程序组件的一个示例。 该组件使用 BizTalk 运行时提供的 XPathReader 类。 这使得代码阅读文档流，直到找到 XPath 表达式。  
  
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
  
## <a name="minimize-orchestration-complexity-to-improve-performance"></a>最小化 orchestration 复杂性以提高性能  
 业务流程的复杂性对性能有显著的影响。 随着业务流程复杂性增加，总体性能会降低。 几乎无限的各种方案，可用于业务流程和每个方案可能涉及的复杂程度各异的业务流程。 避免复杂的业务流程时可能考虑的模块化方法。 换而言之，将你的业务逻辑拆分为多个可重用的业务流程。  
  
 如果需要实现复杂的业务流程，可以定义消息和变量，内部作用域，只要有可能到而不是在根级别。 此方法会保持在内存中为每个业务流程更小的空间，因为变量和消息时，将释放的流离开已定义的变量和消息的范围。 当业务流程将保存到持久性点 MessageBox 时，这种方法是特别有益。  
  
## <a name="use-the-call-orchestration-shape-versus-the-start-orchestration-shape-to-improve-performance"></a>使用与启动 Orchestration 形状调用业务流程形状来提高性能  
 避免**启动 Orchestration**调整和使用**调用 Orchestration**形状以执行嵌套的业务流程。 事实上，**调用 Orchestration**形状可以用于以同步方式调用另一个项目中引用的业务流程。 此方法允许在 BizTalk 项目之间的重复使用的常见业务流程工作流模式。 当调用另一个嵌套的业务流程的情况下同步**调用 Orchestration**形状，等待嵌套业务流程中，若要完成后才能继续的封闭的业务流程。 在运行调用业务流程的相同线程上执行嵌套的业务流程。  
  
 **启动 Orchestration**形状是类似于**调用 Orchestration**形状，但在这种情况下以异步方式调用嵌套业务流程： 中调用的控制流业务流程继续执行后续调用，而无需等待调用的业务流程，以完成其工作。 为了实现此调用方和被调用的业务流程，间的分离**启动 Orchestration**实现通过发布到 BizTalk Messagebox 的消息。 而执行嵌套的业务流程的进程内 BizTalk 主机实例然后使用此消息。 如果可能，请使用**调用 Orchestration**，特别是当调用的业务流程需要等待才能继续处理嵌套的业务流程的结果。  有关使用调用业务流程形状的详细信息，请参阅 BizTalk Server 2010 文档中的以下主题：  
  
-   [使用在业务流程中的直接绑定端口](http://go.microsoft.com/fwlink/?LinkId=139902)(http://go.microsoft.com/fwlink/?LinkId=139902)。  
  
-   [嵌套业务流程](http://go.microsoft.com/fwlink/?LinkId=139903)(http://go.microsoft.com/fwlink/?LinkId=139903)。  
  
## <a name="use-xmlreader-with-xlangmessage-versus-using-xmlreader-with-xmldocument-to-improve-orchestration-performance"></a>XmlReader 使用 XLANGMessage 与使用 XmlReader XmlDocument 来改善业务流程  
 要提高.NET 调用的方法从业务流程的业务流程性能，请使用带有 XLANGMessage，不 XmlDocument XmlReader。 下面的代码示例说明了此功能。  
  
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
  
 另一种方法就是创建基于架构的.NET 类。 这将使较少的内存比加载到文档**XmlDocument**对象，以及为.NET 开发人员提供轻松访问的架构元素。 若要生成基于 BizTalk 架构的类，可以使用与 Visual Studio 提供的 xsd.exe 工具。 例如，运行**xsd.exe \<schema.xsd >/类**ItemB，ItemC，将针对简单架构包含名为 ItemA 的字段，生成下面的类。  
  
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
  
 此类然后中.NET 程序集才能访问消息元素中，引用和返回的对象可以直接分配给消息。 下面是类的生成上面的一个用法示例。  
  
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
  
 此方法允许你在处理消息时使用的面向对象的方法。 此方法应主要用于相对较小的消息。 这是因为即使此方法使用少得多的内存比时加载到消息**XmlDocument**对象，整个消息，则仍加载到内存。 当处理更大的消息时，使用**XmlReader**类来读取消息和**XmlWriter**类将消息写入。 使用时**XmlReader**和**XmlWriter**，消息包含在**VirtualStream**对象。 如果消息大小超过指定的值**大型消息阈值 （字节）** ，则公开的 BizTalk 组属性配置页上，将消息写入到文件系统。 这会降低整体性能，但是避免内存不足异常。  
  
## <a name="improve-performance-by-minimizing-the-use-of-logical-ports-bound-to-physical-ports"></a>通过使用绑定到的物理端口的逻辑端口最大限度提高性能  
 可以通过将绑定到使用以下适配器的物理端口的逻辑端口的使用降至最低来提高性能：  
  
-   SQL Server、 Oracle  
  
-   WSE，HTTP，WCF  
  
-   MSMQ MQSeries  
  
 在 BizTalk Server 2010 中，发送和接收管道可以直接从业务流程使用 Microsoft.XLANGs.Pipeline.dll 中包含的 XLANGPipelineManager 类调用。 因此，管道处理可以变为从端口业务流程;业务流程中的逻辑端口可以替换调用给定的.NET 类的实例 （例如，使用 ADO.NET 数据访问组件） 是表达式形状。 在采用此方法之前, 应该注意，如果不使用适配器和物理端口，你会失去利用其函数，如批处理、 重试次数、 声明性配置和辅助传输协议的能力。  
  
## <a name="orchestration-design-patterns"></a>业务流程设计模式  
 业务流程设计器允许开发人员实现范围广泛的企业集成模式。 一些常见模式包括聚合器、 异常处理和补偿、 消息代理、 散点图和收集，并按顺序和并行的队列。 可以利用这些模式来开发复杂的企业应用程序集成 (EAI)、 面向服务体系结构 (SOA) 和业务流程管理 (BPM) 解决方案与 BizTalk Server。 有关业务流程设计模式的详细信息，请参阅主题[实现在业务流程中的设计模式](http://go.microsoft.com/fwlink/?LinkId=140042)(http://go.microsoft.com/fwlink/?LinkId = 140042) BizTalk Server 文档中和[模式和最佳实践企业集成](http://go.microsoft.com/fwlink/?LinkId=140043)(http://go.microsoft.com/fwlink/?LinkId = 140043)。  
  
## <a name="make-appropriate-use-of-net-classes-in-orchestrations-to-maximize-performance"></a>在业务流程来最大化性能中请适当地使用.NET 类  
 一般情况下，使用内部业务流程的.NET 类可以划分为两个不同类别：  
  
-   **帮助程序和服务-**这些类提供对业务流程，例如跟踪、 错误处理、 缓存和序列化/反序列化的公共服务。 大多数这些类可以作为与任何内部状态和多个公共静态方法的静态类实现。 此方法可避免在不同的业务流程运行在同一时间，这有助于减少主机进程的工作空间和保存内存中创建多个对象的同一个类。 无状态的类可帮助减少必须序列化和业务流程是已冻结时保留到 BizTalk MessageBox 的内部状态的总体大小。  
  
-   **实体和业务对象-**可以使用这些类以管理实体，例如订单、 订单项和客户。 单个业务流程内部可以创建和管理多个相同类型的实例。 这些类是通常有状态的并公开公共字段和/或方法，以便修改对象的内部状态以及属性。 这些类的实例可以通过反 XLANGMessage 部分序列化为.NET 对象，通过使用动态创建**XmlSerializer**或**DataContractSerializer**类或通过使用**XLANGPart.RetrieveAs**方法。 您构建业务流程使用有状态的类的实例的创建尽可能后期和不再需要后立即释放方式中的非事务性作用域。 此方法减少主机进程的工作空间，并最大程度减少已冻结业务流程时持久化到 MessageBox 数据库的序列化的内部状态的总体大小。 有关使用 BizTalk Server 中的业务流程的详细信息，请参阅文章[适用的 BizTalk Server 业务流程的常见问题](http://go.microsoft.com/fwlink/?LinkID=116886)(http://go.microsoft.com/fwlink/?LinkID=116886)。  
  
    > [!NOTE]  
    >  虽然此文章 BizTalk Server 2004 和 BizTalk Server 2006 编写的介绍的概念将还适用于 BizTalk Server 2010 业务流程中。  
  
## <a name="orchestration-exception-handler-blocks"></a>业务流程异常处理程序块  
 使用业务流程异常处理程序块时，包含在一个或多个作用域 （非事务作用域尽可能） 的所有业务流程形状，并至少创建以下异常处理程序块：  
  
-   异常处理程序块中处理泛型 System.Exception 错误。  
  
-   异常处理程序块中处理了一般异常，以便捕获和处理可能的非托管的错误，例如 COM 异常。  
  
 有关使用 Orchestration 异常处理块的详细信息，请参阅以下文章：  
  
-   [使用 BizTalk Server 异常处理](http://msdn.microsoft.com/library/aa561229.aspx)(http://msdn.microsoft.com/library/aa561229.aspx)。  
  
-   [Charles Young 博客，BizTalk Server 2006： 补偿模型](http://go.microsoft.com/fwlink/?LinkId=158017)(http://go.microsoft.com/fwlink/?LinkId=158017)。  
  
    > [!NOTE]  
    >  而使用编写的此博客[!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)]记住，博客中所述的原则也适用于[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]。  
  
## <a name="considerations-when-using-maps-in-orchestrations"></a>在业务流程中使用地图时的注意事项  
 在业务流程中使用地图时，应考虑以下事项：  
  
-   如果使用映射要提取或设置与使用的属性中业务流程，业务逻辑使用可分辨的字段，或升级的属性。 应遵循这种做法，因为如果提取或设置文档的与映射的值加载到内存但是当使用区分字段，或升级的属性，则业务流程引擎将访问消息上下文并不会加载文档读入内存。  
  
-   如果正在使用映射将多个字段聚合为一个字段，请将可分辨字段或升级属性与业务流程变量结合使用，以累计结果集。  
  
## <a name="see-also"></a>另请参阅  
 [优化性能](../technical-guides/optimizing-performance.md)