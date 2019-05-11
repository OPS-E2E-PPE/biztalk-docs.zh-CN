---
title: BizTalk Server 项目版本控制 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: dcdd5354-6335-4320-adbf-28ac934c9ce6
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d7efbbb45b3d2054c3ed71323f0d8bd128db55e0
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530400"
---
# <a name="biztalk-server-project-versioning"></a>BizTalk Server 项目版本控制
当使用进行开发时[!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)]，版本控制受一组标准的规则，它们共同以版本号更改的影响降至最低。 具体取决于如何[!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)]应用程序或组件的部署，可以处理依赖项，通过应用程序配置文件，通过 XCOPY 安装或由其他[!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)]部署机制。 如以下部分所示，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将其他复杂问题添加到版本控制和依赖项。  

## <a name="implications-of-changing-version-numbers"></a>更改版本号的影响  
 在[!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)]开发通常与当前更新程序集的版本号进行生成时生成号。 但是，当开发 BizTalk 解决方案，则更改程序集的版本号可能会中断程序集和引用其程序集版本号的 DLL 的依赖项之间的关系。 下表列出了项，请参阅[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]通过使用其版本号和更改程序集版本号的影响的程序集。  


|                               实体                               |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               更改程序集版本号的效果                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
|--------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                           绑定文件                            |                                                                                                                                                                                                           更改程序集版本会导致引用程序集失败的任何现有绑定文件。 这是因为绑定文件的属性，包括其版本号引用程序集。<br /><br /> 可以使用记事本或其他编辑器更新绑定文件中的版本信息。 可以重新部署该解决方案，并使用，然后重新生成绑定文件[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。 最后，可以使用脚本自动执行部署和版本控制。 有关部署的详细信息，请参阅[部署和管理 BizTalk 应用程序](../core/deploying-and-managing-biztalk-applications.md)。                                                                                                                                                                                                            |
|            BAM 跟踪配置文件定义 (.btt) 文件            |                                                                                                                                                                                                                                                                                                                                           更改程序集版本会导致任何现有 BAM 跟踪配置文件定义文件失败。 BAM 跟踪文件为二进制文件格式的因此它们不能进行编辑，而是必须重新生成。 如果需要 BAM 跟踪配置文件，则可能需要执行以下任一操作：<br /><br /> -避免在生成过程中经常更新版本号。<br />-生成 BAM 跟踪配置文件，等到版本号稳定的延迟。                                                                                                                                                                                                                                                                                                                                            |
| 通过使用 Web Services 发布向导发布的 web 服务 | 当 Web Services 发布向导用于生成 ASP.NET Web 接口的程序集版本[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]程序集包含在 ASP.NET 源代码。 程序集的版本号用作在运行时由 ASP.NET 接口的一部分**bodyTypeAssemblyQualifiedName** Web 服务操作的属性。 如果版本号[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]而不更新的程序集更改**bodyTypeAssemblyQualifiedName**属性，则后续的 Web 服务操作将被拒绝[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。<br /><br /> 如果接收位置使用 XmlDefaultPipeline，则订阅依赖于文档类型。 它使用嵌入的程序集信息，如果该程序集不存在，则将失败。 如果使用 PassThruPipeline (公开某一端口并让向导创建接收位置的情况下时的默认值），则订阅会忽略此嵌入的程序集信息。 |

 若要详细了解如何[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]程序集和部署，请参阅[BizTalk 程序集](../core/biztalk-assemblies.md)。  

## <a name="approaches-to-versioning"></a>版本控制方法  
 在规划项目时，您可以在以下选择：  

- 选择固定的程序集版本为给定可交付结果和的文件版本号递增  

- 开发过程中递增程序集版本和文件版本  

  下表中，这些方法进行比较。  

|                                                                    固定的程序集版本，动态文件版本                                                                     |                                                            动态程序集版本，固定或动态文件版本                                                            |
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                                                程序集版本号 = 固定的版本号<br /><br /> 文件版本号 = 内部版本号                                                |                                             程序集版本号 = 内部版本号<br /><br /> 文件版本号 = 内部版本号                                             |
|   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 如果安装了多个程序集，运行时可能会选取错误的程序集的版本。    | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 始终运行最新版本的程序集，即使安装了多个程序集。 |
|                                                            可以在任何时间部署解决方案的只有一个版本。                                                            |               （尽管该解决方案，如架构定义的其他方面可能会发生冲突），可以并列部署解决方案的不同版本。                |
|                                                   BizTalk 主机需要重新启动以强制加载更新的程序集。                                                    |                               强制[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]加载新程序集。                               |
| 需要较少的工作来创建新的部署，因为引用的程序集版本号 （例如，绑定文件和跟踪配置文件） 的文件不需要对其进行编辑。 |                   要求的详细信息适用于部署因为文件的引用程序集版本需要保留的最新版本进行更新。                    |

 您可以选择使用固定的程序集版本和动态文件版本方法，如果您是在设计系统原型或开发任何其他类型的非交付项目。 如果不打算交付给最终用户应用程序，可以简化部署任务的安排并减少中断依赖项修复程序集版本和递增文件版本号。 对于版本跟踪，您必须记得递增每个生成的文件版本号。  

 如果要生成的项目，将直接发送到最终用户，则应考虑递增程序集的版本号，并 （可选） 将存储有意义的文件版本号。 虽然此方法需要更多的修改内部版本号和关联的依赖关系工作，它可确保使用您的程序集的最新版本。 通过使用自动的部署脚本，可以减少版本控制的影响。 若要查看部署示例，请参阅[应用程序部署 （BizTalk Server 示例文件夹）](../core/application-deployment-biztalk-server-samples-folder.md)。  

> [!NOTE]
>  应选择可确保传递正确的文件的版本控制机制并简化维护和增强功能。  

## <a name="map-function-version-numbering"></a>映射功能版本编号  
 .NET 程序集可以从调用在映射内使用**脚本**functoid。 这提供了大量的灵活性，并使开发者能够解决很多不同的自定义映射问题。 它还规定了在地图上的唯一约束，它必须在内部引用程序集类型名称不仅还正在调用的完整的程序集版本号。 因此，如果更改了映射所调用的程序集的版本号，所有引用程序集的链接将中断。  

 若要避免此问题，我们建议，如果需要从映射调用程序集，特定的程序集创建来保存仅映射功能，并修复此程序集的程序集版本号。 这样一来，其他帮助器函数可以更新而无需中断映射的程序集版本。  

 如果通过该映射引用的程序集更改映射开发完成后请考虑更新以反映已更新的版本号在映射编辑器外映射文件。  

#### <a name="to-use-notepad-to-modify-the-map-file-to-reflect-updated-version-numbers"></a>若要使用记事本修改映射文件以反映已更新的版本号  

1.  使用**启动**菜单上，启动记事本。  

2.  在记事本中，在**文件**菜单上，单击**打开**。 在中**开放**对话框中，选择该映射文件您想要修改，然后单击**打开**。  

3.  在 **“编辑”** 菜单中，单击 **“查找”**。 在中**查找**对话框框中，输入**程序集 =**，然后单击**查找下一个**。  

4.  如果没有对外部程序集的脚本引用，记事本应该找到如下所示的 XML 元素：  

    ```  
    <Script Language="ExternalAssembly" Assembly="Contoso.Scripts, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c5145e4e089" Class="Contoso.Scripts" Function="CalculateValue" AssemblyPath="Contoso.Scripts.dll"/>  
    ```  

     更新的版本号。 如果有多个实例，使用**替换为**上**编辑**菜单。  

5.  保存该文件。  

     现在可以打开用映射编辑器的映射。  

## <a name="see-also"></a>请参阅  
 [部署 BizTalk 应用程序的最佳做法](../core/best-practices-for-deploying-a-biztalk-application.md)   
 [Admin （BizTalk Server 示例文件夹）](../core/admin-biztalk-server-samples-folder.md)   
 [以编程方式部署和启动业务流程的新版本](../core/deploying-and-starting-a-new-version-of-an-orchestration-programmatically.md)