---
title: 使用 WCF LOB 适配器 SDK 的已知问题 |Microsoft Docs
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
ms.openlocfilehash: 4142612b58c4978da1e97c69e112b91f19509fe9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65363591"
---
# <a name="known-issues-with-the-wcf-lob-adapter-sdk"></a>WCF LOB 适配器 SDK 的已知的问题
本主题介绍与关联的已知的问题[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]。 它还为这些问题提供解决方法。  
  
## <a name="unable-to-change-sdk-features-using-add-or-remove-programs"></a>无法更改 SDK 功能使用添加或删除程序
 **问题**:使用**添加或删除程序**控制面板中无法更改的功能[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]运行 Windows Vista 的计算机上。  
  
 **解析**:而不是使用**添加或删除程序**要修改您的安装，请重新运行 Setup.exe 程序。  
  
## <a name="base-runtime"></a>基本运行时  
  
### <a name="applications-using-transactions-in-asynchronous-proxy-must-explicitly-call-proxyopen"></a>使用异步代理中的事务的应用程序必须显式调用 Proxy.Open  
 **问题**:使用异步代理中的适配器使用的事务的应用程序必须显式调用代理。打开以进行流动的事务。  
  
 **解析**:由生成代理后，可以完成这[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]在客户端程序中所示：  
  
```  
EchoAdapterClient echoAdapterProxy = new EchoAdapterClient("mEchoConfiguration");  
echoAdapterProxy.Open();  
...  
```  
  
### <a name="iduplexchannel-shape-not-supported"></a>IDuplexChannel 形状不受支持  
 **问题**:在此版本中不支持 IDuplexChannel 通道形状。  
  
 **解析**:使用 WCF 通道模型来创建支持双工信道的 WCF 自定义绑定。  
  
### <a name="request-schema-generated-with-or-without-in-or-out-parameters"></a>生成带或不带 In 或 Out 参数的请求架构  
 **问题**:在中**ExportInputXmlSchema**类的方法**OperationMetadata**，始终生成请求架构，即使它不能包含任何 in 或 out 参数。  
  
### <a name="providing-multiple-operation-namespaces"></a>提供多个操作命名空间  
 **问题**:如果适配器开发人员提供了一个操作组的多个操作命名空间[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]生成无效的 WSDL。 生成的输入和输出消息部分的每个操作不会链接到正确的架构引用。  
  
 **解析**:确保每个 OperationMetadata.OperationGroup 已映射到单个 OperationMetadata.OperationNamespace。  
  
### <a name="overloaded-operations-not-supported"></a>不支持重载的操作  
 **问题**:在此版本中，动态的协定生成器 （WSDL 生成器） 组件的 sdk 不支持重载的操作，即，具有相同名称但不同的签名操作。  
  
### <a name="fault-contract-not-supported"></a>不支持的错误协定  
 **问题**:在此版本中，动态的协定生成器 （WSDL 生成器） 组件的 sdk 不支持错误协定元数据。  
  
### <a name="failure-when-receiving-messages"></a>在接收消息时失败  
 **问题**:在接收时，则适配器时处理特定消息，如果失败的可能**接收超时**绑定属性设置为较小的值。 返回的错误将特定于您的适配器。  
  
 **解决方法**：设置**接收超时**属性绑定到较大的值，例如 23:59:59，它最大值。  
  
### <a name="adapter-stalls-during-message-processing"></a>消息处理过程中适配器停止  
 **问题**:如果有大量的到适配器的请求，处理的工作项可能看起来停止。  
  
 打开新连接时，适配器将队列将由.NET 线程池处理的工作项。 一旦打开连接，进一步排队的工作项来处理每条消息。 如果已用尽线程池，可能发生死锁，其中打开新连接的请求正在阻止要处理的消息的请求。  
  
 **解析**:最终请求会超时并且将继续处理，但是建议的解决方法是可以减少要处理或增加 threadpool 中的线程数的消息数。  
  
 若要增加的线程数，请修改的值[ProcessModelSection.MaxWorkerThreads 属性](https://msdn.microsoft.com/library/system.web.configuration.processmodelsection.maxworkerthreads.aspx)。  
  
## <a name="design-time-proxy-and-schema-generation-tools"></a>设计时代理和架构生成工具  
  
### <a name="limitations-with-select-contract-type"></a>使用选择的协定类型的限制  
 **问题**:"选择协定类型"筛选应用于类别树和可用操作列表。 如果适配器使用者选择包含入站和出站操作的类别节点，所有这些将是 WSDL 和生成的代理，而不考虑"选择协定类型"筛选的一部分。  
  
 **解析**:选择而不是选择整个类别的单个操作。  
  
### <a name="error-with-add-adapter-service-reference-visual-studio-plug-in"></a>错误使用添加适配器服务参考 Visual Studio 插件  
 **问题**:在 BizTalk 项目在 Visual Studio 中，如果已通过使用生成代理[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]，从同一适配器生成另一个代理将生成此错误："命名空间\<全局命名空间\>已经包含 {协定 name} 的定义时编译项目。"  
  
 此版本中不允许编辑的代理。  
  
 **解析**:在 BizTalk 项目中删除多余的代理文件。 如果其他操作需要包含在生成的代理，请删除代理文件，并使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]搜索或浏览元数据，并重新生成代理。  
  
### <a name="error-with-consume-adapter-service-biztalk-project-add-in"></a>错误使用适配器服务的 BizTalk 项目外接程序  
 **问题**:如前面的问题中所示在 BizTalk 项目在 Visual Studio 中，如果从生成的架构中存在公共类型[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]，BizTalk 项目无法进行编译。  
  
 **解析**:在 BizTalk 项目中删除多余的 XML 架构文件，使用使用适配器服务引用搜索或浏览所需的元数据，并重新生成新的 XML 架构文件。  
  
### <a name="error-with-rootnode-typename-in-biztalk-projects"></a>使用 BizTalk 项目中的 RootNode TypeName 错误  
 **问题**:在 BizTalk 项目在 Visual Studio 中，如果从生成的架构[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]包含无效字符或保留的字**RootNode TypeName**属性，在编译时将发生以下错误："节点\<节点引用\>-指定有效的.NET 类型名为此根节点。  此根节点的当前.NET 类型名无效 (它是保留的 BizTalk 关键字或是一个无效C#标识符)。  
  
 **解析**:选择在错误中引用的根节点，并在属性，删除任何非法字符或从保留的字**RootNode TypeName**属性。  
  
### <a name="metadata-generation-tool-limitations"></a>元数据生成工具限制  
 **问题**:如果适配器开发人员提供了在 XML 架构结构 OperationMetadata 和/或 TypeMetadata 派生的类，和 XML 架构包含构造，忽略或禁止通过 datacontractserializer 实现，则元数据生成工具将回退使用用于序列化 XmlSerializer。  
  
 **解析**:请在架构中，删除已禁止的构造或使用[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]元数据对象模型以生成符合 DataContractSerializer 的 XML 架构定义。  
  
### <a name="binding-name-property-does-not-take-effect"></a>绑定名称属性不会生效  
 **问题**:在更改绑定名称属性**绑定属性-常规**选项卡**添加适配器服务引用**对话框将不会生效。  
  
 **解析**:使用 AdapterBinding 派生类，以更改名称，如下所示：  
  
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
  
### <a name="timeout-when-retrieving-metadata"></a>检索元数据时的超时  
 **问题**:如果适配器包含很多操作，如使用工具检索元数据时，您可能会遇到超时[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]，WCF 适配器服务开发向导，或[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]如果尝试进行一次检索许多操作。  
  
 **解析**:减少选择的操作数目。  
  
### <a name="avoid-generating-schemas-which-reference-an-external-import"></a>避免引用外部导入的生成架构  
 **问题**:应避免生成包含对外部导入的一个或多个引用的架构。 如果此操作后，将不带有外部链接。  
  
## <a name="setup"></a>安装  
  
### <a name="setup-halts-while-checking-disk-space"></a>安装程序检查磁盘空间时暂停  
 **问题**:安装时[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]，可能会收到对话框框，表明安装程序正在检查可用磁盘空间，并且安装程序将停止。  
  
 **解析**:发生此问题时，您可以解决此问题通过执行无提示安装[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]在命令提示符。 例如：  
  
```  
Msiexec.exe /package AdapterFramework.msi /qr  
```  
  
### <a name="biztalk-server-developer-tools-required"></a>所需的 BizTalk Server 开发人员工具  
 **问题**:当目标系统具有 Visual Studio 和 Microsoft BizTalk Server，而无需开发人员工具时[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]安装程序将失败。 这是因为它要求 BizTalk Server 开发人员工具是计算机上存在，才能安装[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]。  
  
 **解析**:确保目标计算机具有与开发人员工具一起安装之前安装的 BizTalk Server [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]。  
  
### <a name="corrupt-biztalk-server-installation-causes-sdk-to-fail"></a>损坏 BizTalk Server 安装会导致失败的 SDK  
 **问题**:BizTalk Server 的损坏的安装可能会导致 SDK 安装失败并出现以下错误："DirectoryNotFound 异常"。  
  
 **解析**:卸载并重新安装 BizTalk Server。  
  
 
## <a name="see-also"></a>请参阅  
 [BizTalk Server 入门](../../core/getting-started-with-biztalk-server.md)