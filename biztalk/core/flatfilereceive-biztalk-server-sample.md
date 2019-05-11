---
title: FlatFileReceive （BizTalk Server 示例） |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 90bd9e8d-6ed9-49c4-8437-c0c8b2a9a78d
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6fcae5883f5230b7cd0e97051707133626c87cb4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65388059"
---
# <a name="flatfilereceive-biztalk-server-sample"></a>FlatFileReceive （BizTalk Server 示例）
FlatFileReceive 示例演示如何使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]平面文件处理成等效的.xml 文件。  

## <a name="what-this-sample-does"></a>本示例的用途  
 此示例将 FFInput 文件夹配置为接收位置。 在一个文件，将此文件夹中，将示例文件 FlatFileReceive_in.txt，如[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]处理该消息在此文件中使用以下步骤序列：  

1.  在接收位置文件夹 ffinput 下的输入文件读取的消息。  

2.  在接收管道中，平面文件拆装器组件消息将从平面文件格式转换为等效的 XML 消息。  

3.  在 MessageBox 数据库中，将消息路由到可以将 XML 消息写入发送适配器文件夹 ffoutput 下的文件发送端口。  

## <a name="how-this-sample-is-designed-and-why"></a>此示例设计方式和原因  
 示例消息的诸多基本设计在此示例中。 必须使用平面文件拆装器和平面文件架构中自定义接收管道拆装平面文件消息。 下表总结了这些和其他设计元素。  


|     设计元素      |                                                                                                                                                                  选择的原因                                                                                                                                                                   |
|-------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 自定义接收管道 | -自定义管道使用平面文件拆装器和平面文件架构转换入站采购订单消息。 平面文件拆装器自身不是管道，配置中的接收管道时不能使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。 |
|    平面文件架构     |                           -定义的所有相同的记录和字段特性 （包括结构） 作为 XML 架构，并提供一种机制，用于定义所有平面文件实例消息转换为等效的 XML 实例所需的平面文件特性消息 （或相反）。                           |
|   订阅筛选器   |                                                                                                        -订阅筛选器执行实际的路由通过捕获符合基于属性的字段的一个或多个条件的消息。                                                                                                         |
|       XMLTransmit       |                                                                                                           -执行基本组装传出 XML 消息在需要时。 PassThruTransmit 管道未提供其他支持。                                                                                                            |

 通过结合这些元素构成一个解决方案，用于接受从接收位置的平面文件格式的采购订单消息并写出到发送位置生成的 XML 表示形式。  

 下列注意事项适用于本示例的设计：  

-   平面文件架构 (PO.xsd) 包含描述采购订单平面文件结构的扩展的标注。 可以进行手动创建这些文件，但可以通过使用平面文件向导生成很多。  

-   平面文件架构使用 elementFormDefault 值 Unqualified。 这会生成正确的结果，但有多余且意外的 XML 命名空间 (xmlns) 限定。 使用 elementformdefault 的 Qualified 值可避免此问题。  

-   XmlTransmit 用作发送管道。 在发送端口中不需要属性降级或其他消息处理时，请使用 PassThruTransmit 管道。  

## <a name="where-to-find-this-sample"></a>本示例所在的位置  
 *\<Samples Path\>* \Pipelines\AssemblerDisassembler\FlatFileReceive\  

 下表显示了本示例中的文件及其用途说明：  


|                   文件                   |                                                                                           Description                                                                                            |
|---------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                 Cleanup.bat                 | 用于取消部署程序集并从全局程序集缓存中删除。 删除发送和接收端口。 根据需要删除 Microsoft Internet 信息服务 (IIS) 虚拟目录。 |
|            FFReceivePipeline.btp            |                       [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 接收管道使用平面文件拆装器组件的文件。                        |
| FlatFileReceive.btproj, FlatFileReceive.sln |                                                                           本示例的项目和解决方案文件。                                                                            |
|           FlatFileReceive_in.txt            |                                                                                        示例输入的文件。                                                                                        |
|         FlatFileReceiveBinding.xml          |                                                                          用于如端口绑定之类的自动化设置。                                                                          |
|                   PO.xsd                    |                                                                                入站平面文件架构。                                                                                 |
|                  Setup.bat                  |                                                                            用于生成和初始化本示例。                                                                             |

## <a name="how-to-use-this-sample"></a>如何使用此示例  
 此示例作为基础用于平面文件处理解决方案。 您可以扩展此示例中使用以适合自己需求的设计元素的很多。  

## <a name="building-and-initializing-this-sample"></a>生成并初始化此示例  

1. 在命令窗口中，导航到以下文件夹：  

    *\<Samples Path\>* \Pipelines\AssemblerDisassembler\FlatFileReceive  

2. 运行文件 Setup.bat，以执行以下操作：  

   - 在文件夹中创建的输入 (FFInput) 和为本示例的输出 (FFOutput) 文件夹：  

      *\<Samples Path\>* \Pipelines\AssemblerDisassembler\FlatFileReceive  

   - 编译并部署本示例的 Visual Studio 项目。  

   - 创建并绑定[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]接收位置、 发送和接收端口。  

     > [!NOTE]
     >  本示例将显示以下警告时创建并绑定端口：`Warning: Receive handler not specified for receive location "FlatFileReceive_RL"; updating with first receive handler with matching transport type.` 您可以放心地忽略这些警告。 （若要应对可能的命名差异在用户安装中，主机名和接收处理程序中已省略绑定文件。）  

   - 启用该接收位置，并启动发送端口。  

> [!NOTE]
>  您应确认[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]未报告任何错误在生成和初始化过程中尝试运行此示例之前。  
> 
> [!NOTE]
>  如果你选择打开并生成本示例中的项目不运行 Setup.bat 的情况下，必须首先创建强名称密钥对使用.NET Framework 强名称实用工具 (sn.exe)。 使用此密钥对生成程序集进行签名。  
> 
> [!NOTE]
>  若要撤消 Setup.bat 所做的更改，请运行 Cleanup.bat。 必须运行 Setup.bat 前运行 Cleanup.bat 时间。  

## <a name="running-this-sample"></a>运行本示例  

1.  将 FlatFileReceive_in.txt 文件的副本放到 FFInput 文件夹下。  

2.  查看在 FFOutput 文件夹中创建的.xml 文件。 输出文件的名称根据消息 ID GUID。 此文件包含在接收文件夹中放置的平面文件的 XML 等效项。  

## <a name="classes-or-methods-used-in-this-sample"></a>类或方法在此示例中使用  
 配置脚本 Setup.bat 和 Cleanup.bat 依赖以下管理的 Windows Management Instrumentation (WMI) 脚本：  

- Start Send Port\StartSendPort.vbs  

- Enable Receive Location\EnableRecLoc  

- 删除发送端口 \removesendport  

  设置和清理批处理文件使用 BTSTask，如下所示：  

- **BTSTask ImportBindings**应用绑定文件并创建应用程序、 端口和绑定  

- **BTSTask RemoveApp，** 用于删除 FlatFileReceiveApplication  

## <a name="see-also"></a>请参阅  
- [Pipelines-AssemblerDisassembler（BizTalk Server 示例文件夹）](../core/pipelines-assemblerdisassembler-biztalk-server-samples-folder.md)   
- [平面文件反汇编程序管道组件](../core/flat-file-disassembler-pipeline-component.md)   
- [平面文件架构](../core/flat-file-schemas.md)   
- [默认管道](../core/default-pipelines.md)   
- **WMI 脚本示例** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]   
- [BTSTask 命令行参考](../core/btstask-command-line-reference.md)   
- [FlatFileSend（BizTalk Server 示例）](../core/flatfilesend-biztalk-server-sample.md)
