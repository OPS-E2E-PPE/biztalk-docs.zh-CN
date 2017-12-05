---
title: "FlatFileReceive （BizTalk Server 示例） |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 90bd9e8d-6ed9-49c4-8437-c0c8b2a9a78d
caps.latest.revision: "20"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: db996437cce8cb6f89fb00b589fcbc95429e72f2
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="flatfilereceive-biztalk-server-sample"></a>FlatFileReceive （BizTalk Server 示例）
FlatFileReceive 示例演示如何使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 将平面文件处理成等效的 .xml 文件。  
  
## <a name="what-this-sample-does"></a>本示例的用途  
 本示例将 FFInput 文件夹配置为接收位置。 在将文件（如示例文件 FlatFileReceive_in.txt）放入此文件夹后，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 将按照以下一系列步骤处理该文件内的消息：  
  
1.  读取接收位置文件夹 FFInput 下的输入文件中的消息。  
  
2.  在接收管道中，平面文件拆装器组件将平面文件格式的消息转换为等效的 XML 消息。  
  
3.  在 MessageBox 数据库中，消息会路由至 FILE 发送端口，该端口将 XML 消息写入到发送适配器文件夹 FFOutput 中的某一文件中。  
  
## <a name="how-this-sample-is-designed-and-why"></a>本示例旨在如何以及为何  
 示例消息反映了本示例的诸多基本设计特征。 平面文件消息必须使用自定义接收管道内的平面文件拆装器和平面文件架构进行拆装。 下表对以上设计元素和其他设计元素进行了总结。  
  
|设计元素|选择的原因|  
|--------------------|--------------------------|  
|自定义接收管道|-自定义管道使用平面文件拆装器和平面文件架构转换入站采购订单消息。 平面文件拆装器自身不是管道，因此在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台中配置接收管道时不能使用平面文件拆装器。|  
|平面文件架构|-定义的所有相同的记录和字段特性 （包括结构） 作为 XML 架构，并提供用于定义所有所需将平面文件实例消息转换为等效的 XML 实例的平面文件特征的机制消息 （或相反）。|  
|订阅筛选器|-订阅筛选器执行实际的路由通过捕获满足基于属性的字段的一个或多个条件的消息。|  
|XMLTransmit|-执行基本的程序集的传出 XML 消息在需要时。 PassThruTransmit 管道不提供其他支持。|  
  
 通过结合这些元素，产生了一个可从接收位置接受平面文件格式的采购订单消息并将生成的 XML 表示形式写出到发送位置的解决方案。  
  
 下列注意事项适用于此示例的设计：  
  
-   平面文件架构 (PO.xsd) 包含描述采购订单平面文件的结构的扩展标注。 可手动创建这些文件，但大多数文件都可以使用平面文件向导生成。  
  
-   平面文件架构使用 elementFormDefault 的 Unqualified 值。 这会生成正确结果，但该结果带有其他意外 XML 命名空间 (xmlns) 限定。 使用 elementFormDefault 的 Qualified 值可避免此问题。  
  
-   XmlTransmit 用作发送管道。 当发送管道中不需要属性降级或其他消息处理时，请使用 PassThruTransmit 管道。  
  
## <a name="where-to-find-this-sample"></a>本示例所在的位置  
 *\<示例路径\>*\Pipelines\AssemblerDisassembler\FlatFileReceive\  
  
 下表显示了本示例中的文件及其用途说明：  
  
|文件|Description|  
|---------------|-----------------|  
|Cleanup.bat|用于取消部署程序集并从全局程序集缓存中删除这些程序集。 删除发送和接收端口。 根据需要删除 Microsoft Internet 信息服务 (IIS) 虚拟目录。|  
|FFReceivePipeline.btp|带平面文件拆装器组件的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 接收管道文件。|  
|FlatFileReceive.btproj、FlatFileReceive.sln|本示例的项目文件和解决方案文件。|  
|FlatFileReceive_in.txt|示例输入文件。|  
|FlatFileReceiveBinding.xml|用于如端口绑定之类的自动化设置。|  
|PO.xsd|入站平面文件的架构。|  
|Setup.bat|用于生成和初始化本示例。|  
  
## <a name="how-to-use-this-sample"></a>如何使用本示例  
 可将本示例用作您自己的平面文件处理解决方案的基础， 并可根据自己的需要扩展本示例中用到的诸多设计元素。  
  
## <a name="building-and-initializing-this-sample"></a>生成并初始化此示例  
  
1.  在命令窗口中，导航到下面的文件夹：  
  
     *\<示例路径\>*\Pipelines\AssemblerDisassembler\FlatFileReceive  
  
2.  运行 Setup.bat 文件，该文件将执行以下操作：  
  
    -   在下面的文件夹中，为本示例创建输入 (FFInput) 和输出 (FFOutput) 文件夹：  
  
         *\<示例路径\>*\Pipelines\AssemblerDisassembler\FlatFileReceive  
  
    -   为本示例编译并部署 Visual Studio 项目。  
  
    -   创建并绑定 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 接收位置、发送和接收端口。  
  
        > [!NOTE]
        >  此示例显示以下警告时创建和绑定端口：`Warning: Receive handler not specified for receive location "FlatFileReceive_RL"; updating with first receive handler with matching transport type.`可以放心地忽略这些警告。 （考虑可能命名在用户安装中，主机名的差异和接收处理程序省略了从绑定文件。）  
  
    -   启用接收位置并启动发送端口。  
  
> [!NOTE]
>  在尝试运行本示例之前，应确认在生成和初始化过程中 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 未报告任何错误。  
  
> [!NOTE]
>  如果你选择打开并生成此示例中的项目，而无需运行 Setup.bat，必须首先创建强名称密钥对使用.NET Framework 强名称工具 (sn.exe)。 使用此密钥对生成的程序集进行签名。  
  
> [!NOTE]
>  若要撤销 Setup.bat 所做的更改，请运行 Cleanup.bat。 在第二个运行 Setup.bat 之前，必须运行 Cleanup.bat，时间。  
  
## <a name="running-this-sample"></a>运行本示例  
  
1.  将 FlatFileReceive_in.txt 文件的副本放到 FFInput 文件夹下。  
  
2.  查看在 FFOutput 文件夹中创建的 .xml 文件。 此输出文件是根据消息 ID GUID 命名的。 此文件包含与接收文件夹中放置的平面文件等效的 XML 文件。  
  
## <a name="classes-or-methods-used-in-this-sample"></a>本示例中使用的类或方法  
 配置脚本 Setup.bat 和 Cleanup.bat 依赖于以下 Windows 管理规范 (WMI) 管理脚本：  
  
-   启动发送端口\StartSendPort.vbs  
  
-   启用接收位置\EnableRecLoc  
  
-   删除发送端口\RemoveSendPort  
  
 安装和清除批处理文件使用以下 BTSTask：  
  
-   **BTSTask ImportBindings**应用绑定文件并创建应用程序、 端口和绑定  
  
-   **BTSTask RemoveApp**删除 FlatFileReceiveApplication  
  
## <a name="see-also"></a>另请参阅  
-  [Pipelines-AssemblerDisassembler（BizTalk Server 示例文件夹）](../core/pipelines-assemblerdisassembler-biztalk-server-samples-folder.md)   
-  [平面文件反汇编程序管道组件](../core/flat-file-disassembler-pipeline-component.md)   
-  [平面文件架构](../core/flat-file-schemas.md)   
-  [默认管道](../core/default-pipelines.md)   
-  **WMI 脚本示例**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]   
-  [BTSTask 命令行参考](../core/btstask-command-line-reference.md)   
-  [FlatFileSend（BizTalk Server 示例）](../core/flatfilesend-biztalk-server-sample.md)