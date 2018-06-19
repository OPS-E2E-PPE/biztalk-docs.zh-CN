---
title: 已知问题 WCF LOB 适配器 SDK |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2cda4248-2efa-4e3d-a5ce-9a57728c51e1
caps.latest.revision: 35
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d718450dfd4db1fd6d695c1a3ecc21f9f1fd8deb
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25968003"
---
# <a name="known-issues-with-the-wcf-lob-adapter-sdk"></a>WCF LOB 适配器 SDK 的已知的问题
本主题介绍与关联的已知的问题[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]。 它还提供某些这些问题的解决方法。  
  
## <a name="unable-to-change-sdk-features-using-add-or-remove-programs"></a>无法更改 SDK 功能使用添加或删除程序
 **问题**： 使用**添加或删除程序**控制面板中无法更改的功能[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]运行 Windows Vista 的计算机上。  
  
 **解析**： 而不是使用**添加或删除程序**若要修改您的安装，重新运行的 Setup.exe 程序。  
  
## <a name="base-runtime"></a>基本运行时  
  
### <a name="applications-using-transactions-in-asynchronous-proxy-must-explicitly-call-proxyopen"></a>在异步代理中使用事务的应用程序必须显式调用 Proxy.Open  
 **问题**： 事务使用异步代理中的适配器的应用程序必须显式调用代理。打开以进行流动的事务。  
  
 **解析**： 这由运行代理后，可以完成[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]在客户端程序中所示：  
  
```  
EchoAdapterClient echoAdapterProxy = new EchoAdapterClient("mEchoConfiguration");  
echoAdapterProxy.Open();  
...  
```  
  
### <a name="iduplexchannel-shape-not-supported"></a>不支持 IDuplexChannel 形状  
 **问题**： 此版本中不支持 IDuplexChannel 通道形状。  
  
 **解析**： 使用 WCF 通道模型来创建 WCF 自定义绑定支持双工通道。  
  
### <a name="request-schema-generated-with-or-without-in-or-out-parameters"></a>生成带有或不带 In 或 Out 参数的请求架构  
 **问题**： 在**ExportInputXmlSchema**类的方法**OperationMetadata**，始终生成的请求架构，即使它不能包含任何 in 或 out 参数。  
  
### <a name="providing-multiple-operation-namespaces"></a>提供多个操作的命名空间  
 **问题**： 如果适配器开发人员提供了一个操作组的多个操作命名空间[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]生成无效的 WSDL。 生成的输入和输出每个操作的消息部分未将链接到正确的架构引用。  
  
 **解析**： 确保将每个 OperationMetadata.OperationGroup 映射到单个 OperationMetadata.OperationNamespace。  
  
### <a name="overloaded-operations-not-supported"></a>不支持重载的操作  
 **问题**： 在此版本中，动态的协定生成器 （WSDL 生成器） 组件的 sdk 不支持重载的操作，即，具有相同的操作名称但不同的签名。  
  
### <a name="fault-contract-not-supported"></a>不支持的错误协定  
 **问题**： 在此版本中，动态的协定生成器 （WSDL 生成器） 组件的 sdk 不支持错误协定元数据。  
  
### <a name="failure-when-receiving-messages"></a>在接收消息时失败  
 **问题**： 在接收时，则在处理特定消息，如果时失败的适配器可能**接收超时**绑定属性设置为较小的值。 返回的错误是特定于你的适配器。  
  
 **解决方法**： 设置**接收超时**将属性绑定到较大的值，例如 23:59:59，这最大值。  
  
### <a name="adapter-stalls-during-message-processing"></a>消息处理期间适配器停止  
 **问题**： 如果有大量的到适配器的请求，处理的工作项可能看起来停止。  
  
 打开新连接时，适配器将通过.NET 线程池处理工作项的排队。 一旦打开某个连接，进一步排队工作项以处理每条消息。 如果已用尽线程池，则可能发生死锁，其中打开新连接请求会阻止处理消息的请求。  
  
 **解析**： 最终请求会超时，处理将继续，但建议的解决方法是可以减少要处理或增大在线程池线程数的消息数。  
  
 若要增加线程数，修改的值[ProcessModelSection.MaxWorkerThreads 属性](https://msdn.microsoft.com/library/system.web.configuration.processmodelsection.maxworkerthreads.aspx)。  
  
## <a name="design-time-proxy-and-schema-generation-tools"></a>设计时代理和架构生成工具  
  
### <a name="limitations-with-select-contract-type"></a>与选择的协定类型的限制  
 **问题**:"选择的协定类型"筛选应用于类别树和可用操作列表。 如果适配器使用者选择包含入站和出站操作的类别节点，所有这些将是 WSDL 和生成的代理，而不考虑"选择的协定类型"筛选的一部分。  
  
 **解析**： 选择而不是选择整个类别的各个操作。  
  
### <a name="error-with-add-adapter-service-reference-visual-studio-plug-in"></a>与错误将添加适配器服务引用 Visual Studio 插件  
 **问题**： 在 Visual Studio 中，如果已通过使用生成代理在 BizTalk 项目[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]，从同一适配器生成另一个代理将生成此错误:"命名空间\<全局命名空间\>已包含 {协定 name} 的定义时编译项目。"  
  
 此版本不允许编辑的代理。  
  
 **解析**： 删除 BizTalk 项目中的外部代理文件。 如果需要包含在生成的代理的其他操作，删除代理文件，并使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]搜索或浏览元数据，并重新生成代理。  
  
### <a name="error-with-consume-adapter-service-biztalk-project-add-in"></a>错误使用适配器 BizTalk Project 外接程序服务  
 **问题**： 以前的问题，如 BizTalk 项目中在 Visual Studio 中，如果公共类型存在于从生成的架构中[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]，BizTalk 项目无法进行编译。  
  
 **解析**: BizTalk 项目中删除多余的 XML 架构文件，使用适配器服务引用用于搜索或浏览所需的元数据，并重新生成新的 XML 架构文件。  
  
### <a name="error-with-rootnode-typename-in-biztalk-projects"></a>与 RootNode TypeName BizTalk 项目中的错误  
 **问题**： 在 Visual Studio 中，如果从架构生成在 BizTalk 项目[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]包含无效字符或保留的字**RootNode TypeName**属性，在将出现以下错误编译时间:"节点\<节点引用\>-指定此根节点的有效.NET 类型名称。  此根节点的当前的.NET 类型名称无效 （它是保留的 BizTalk 关键字，或为无效的 C# 标识符）。  
  
 **解析**： 选择此错误中引用的根节点，并在属性中，删除任何非法字符或保留的字从**RootNode TypeName**属性。  
  
### <a name="metadata-generation-tool-limitations"></a>元数据生成工具限制  
 **问题**： 如果适配器开发人员提供了在 XML 架构结构 OperationMetadata 和/或在派生类，并将 XML 架构包含构造忽略或禁止 DataContractSerializer，元数据生成工具回退使用 XmlSerializer 进行序列化。  
  
 **解析**： 在架构中删除禁止的构造，或使用[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]元数据对象模型，以便生成符合 DataContractSerializer 的 XML 架构定义。  
  
### <a name="binding-name-property-does-not-take-effect"></a>绑定名称属性将不会生效  
 **问题**： 在上更改的绑定名称属性**绑定属性-常规**选项卡**添加适配器服务引用**对话框中将不会生效。  
  
 **解析**： 使用 AdapterBinding 派生类更改的名称，如下所示：  
  
```  
[Browsable(false)]  
public new virtual string Name  
{  
     set  
     {  
          base.Name = value;  
     }  
     get  
     {  
          return base.Name;  
     }  
}  
```  
  
### <a name="timeout-when-retrieving-metadata"></a>检索元数据时超时  
 **问题**： 如果适配器包含许多操作，如使用工具检索元数据时，你可能会遇到超时[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]，WCF 适配器服务开发向导中，或[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]如果你尝试检索在许多操作一次。  
  
 **解析**： 减少选择的操作的数目。  
  
### <a name="avoid-generating-schemas-which-reference-an-external-import"></a>避免生成架构引用的外部导入  
 **问题**： 应避免生成包含对外部导入的一个或多个引用的架构。 如果此操作后，将不可以执行的外部链接。  
  
## <a name="setup"></a>安装  
  
### <a name="setup-halts-while-checking-disk-space"></a>安装程序检查磁盘空间时的暂停  
 **问题**： 在安装时[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]，你可能会收到一个说明对话框安装程序正在检查可用磁盘空间和安装程序将不会继续。  
  
 **解析**： 发生此问题时，你可以通过执行无提示安装的要解决此问题[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]在命令提示符。 例如：  
  
```  
Msiexec.exe /package AdapterFramework.msi /qr  
```  
  
### <a name="biztalk-server-developer-tools-required"></a>BizTalk Server 所需的开发人员工具  
 **问题**： 当目标系统而无需开发人员工具，具有 Visual Studio 和 Microsoft BizTalk Server[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]安装程序将失败。 这是因为它需要 BizTalk Server 开发人员工具，以在计算机上安装[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]。  
  
 **解析**： 请确保目标计算机具有与开发人员工具安装在安装之前的 BizTalk Server [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]。  
  
### <a name="corrupt-biztalk-server-installation-causes-sdk-to-fail"></a>损坏 BizTalk Server 安装原因无法正常工作的 SDK  
 **问题**: BizTalk server 损坏的安装可能会导致 SDK 安装失败并出现以下错误:"DirectoryNotFound 异常"。  
  
 **解析**： 卸载并重新安装 BizTalk Server。  
  
 
## <a name="see-also"></a>另请参阅  
 [BizTalk Server 入门](../../core/getting-started-with-biztalk-server.md)