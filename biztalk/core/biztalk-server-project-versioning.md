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
ms.openlocfilehash: 6fb331e7809ec7517070a448283823ffd69dc8d8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36984486"
---
# <a name="biztalk-server-project-versioning"></a>BizTalk Server 项目版本控制
当使用进行开发时[!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)]，版本控制受一组标准的规则，它们共同以版本号更改的影响降至最低。 具体取决于如何[!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)]应用程序或组件的部署，可以处理依赖项，通过应用程序配置文件，通过 XCOPY 安装或由其他[!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)]部署机制。 如以下部分所示，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将其他复杂问题添加到版本控制和依赖项。  

## <a name="implications-of-changing-version-numbers"></a>更改版本号的隐患  
 在[!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)]开发通常与当前更新程序集的版本号进行生成时生成号。 但在开发 BizTalk 解决方案时，更改程序集版本号会中断程序集与通过其程序集版本号引用 DLL 的依赖项之间的关系。 下表列出了项，请参阅[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]通过使用其版本号和更改程序集版本号的影响的程序集。  


|                               实体                               |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               更改程序集版本号的影响                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
|--------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                           绑定文件                            |                                                                                                                                                                                                           更改程序集版本号会导致引用该程序集的所有现有绑定文件失败。 这是因为绑定文件通过包括版本号在内的属性来引用程序集。<br /><br /> 可以使用记事本或其他编辑器更新绑定文件中的版本信息。 可以重新部署该解决方案，并使用，然后重新生成绑定文件[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。 最后，可以使用脚本来进行自动化部署和版本控制。 有关部署的详细信息，请参阅[部署和管理 BizTalk 应用程序](../core/deploying-and-managing-biztalk-applications.md)。                                                                                                                                                                                                            |
|            BAM 跟踪配置文件定义 (.btt) 文件            |                                                                                                                                                                                                                                                                                                                                           更改程序集版本号会导致所有现有 BAM 跟踪配置文件定义文件失败。 BAM 跟踪文件采用二进制文件格式，因此不能进行编辑，而只能重新生成。 如果需要 BAM 跟踪文件，则可能需要执行以下任一操作：<br /><br /> -避免在生成过程中经常更新版本号。<br />-生成 BAM 跟踪配置文件，等到版本号稳定的延迟。                                                                                                                                                                                                                                                                                                                                            |
| 通过使用 Web Services 发布向导发布的 Web Services | 当 Web Services 发布向导用于生成 ASP.NET Web 接口的程序集版本[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]程序集包含在 ASP.NET 源代码。 程序集的版本号用作在运行时由 ASP.NET 接口的一部分**bodyTypeAssemblyQualifiedName** Web 服务操作的属性。 如果版本号[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]而不更新的程序集更改**bodyTypeAssemblyQualifiedName**属性，则后续的 Web 服务操作将被拒绝[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。<br /><br /> 如果接收位置使用 XmlDefaultPipeline，则订阅依赖于文档类型。 订阅使用嵌入的程序集信息，并会在程序集不存在时失败。 如果使用 PassThruPipeline（公开某一端口并让向导创建接收位置时的默认值），则订阅会忽略此嵌入的程序集信息。 |

 若要详细了解如何[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]程序集和部署，请参阅[BizTalk 程序集](../core/biztalk-assemblies.md)。  

## <a name="approaches-to-versioning"></a>版本控制方法  
 在规划项目时，可以在以下方法中进行选择：  

- 为给定的可交付结果选择一个固定的程序集版本，并只以增量方式更改文件的版本号  

- 在开发过程中同时以增量方式更改程序集版本和文件版本  

  下表对这两种方法进行了比较。  

|                                                                    固定的程序集版本，动态的文件版本                                                                     |                                                            动态的程序集版本，固定或动态的文件版本                                                            |
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                                                程序集版本号 = 固定版本号<br /><br /> 文件版本号 = 内部版本号                                                |                                             程序集版本号 = 内部版本号<br /><br /> 文件版本号 = 内部版本号                                             |
|   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 如果安装了多个程序集，运行时可能会选取错误的程序集的版本。    | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 始终运行最新版本的程序集，即使安装了多个程序集。 |
|                                                            在任何时候只能部署解决方案的一个版本。                                                            |               可以并列部署解决方案的不同版本（尽管解决方案的其他特征（如架构定义）可能会发生冲突）。                |
|                                                   需要重新启动 BizTalk 主机以强制加载已更新的程序集。                                                    |                               强制[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]加载新程序集。                               |
| 由于无需编辑引用程序集版本号的文件（例如绑定文件和跟踪配置文件），因此进行新部署的工作量较轻。 |                   由于需要不断地使用新版本来更新引用程序集版本号的文件，因此部署的工作量较重。                    |

 在设计系统原型或开发任何其他非交付项目时，可以选择使用固定程序集版本和动态文件版本方法。 如果不打算将应用程序交付给最终用户，则可以通过固定程序集版本和以增量形式更改文件版本号的方法来简化部署并减少中断的依存关系。 对于版本跟踪，必须记住为每个内部版本以增量形式更改文件版本号。  

 如果要生成交付给最终用户的项目，则应考虑以增量方式更改程序集版本号，也可以存储一个有意义的文件版本号。 虽然此方法需要进行更多的工作来修改内部版本号和相关联的依存关系，但它可以确保使用最新的程序集。 通过使用自动部署脚本，可以减少版本控制的影响。 若要查看部署示例，请参阅[应用程序部署 （BizTalk Server 示例文件夹）](../core/application-deployment-biztalk-server-samples-folder.md)。  

> [!NOTE]
>  应该选择可以确保交付正确文件且简化维护和增强功能的版本控制机制。  

## <a name="map-function-version-numbering"></a>映射功能版本编号  
 .NET 程序集可以从调用在映射内使用**脚本**functoid。 这样做非常灵活，并可以使开发者能够解决很多不同的自定义映射问题。 它还规定了在地图上的唯一约束，它必须在内部引用程序集类型名称不仅还正在调用的完整的程序集版本号。 因此，如果更改了映射所调用的程序集版本号，则所有引用该程序集的链接都将中断。  

 为了避免这种情况，建议在需要从映射调用程序集时，创建一个只包含映射功能的特定程序集，并且让该程序集的程序集版本号固定不变。 这样，其他帮助器函数可以更新程序集的版本，而不会中断映射。  

 如果映射开发完成后更改了通过该映射引用的某个程序集，则应考虑在映射编辑器外更新该映射文件，使之反映已更新的版本号。  

#### <a name="to-use-notepad-to-modify-the-map-file-to-reflect-updated-version-numbers"></a>使用记事本修改映射文件以反映更新的版本号  

1.  使用**启动**菜单上，启动记事本。  

2.  在记事本中，在**文件**菜单上，单击**打开**。 在中**开放**对话框中，选择该映射文件您想要修改，然后单击**打开**。  

3.  在 **“编辑”** 菜单中，单击 **“查找”**。 在中**查找**对话框框中，输入**程序集 =**，然后单击**查找下一个**。  

4.  如果存在对外部程序集的脚本引用，则记事本应该找到一个类似如下所示的 XML 元素：  

    ```  
    <Script Language="ExternalAssembly" Assembly="Contoso.Scripts, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c5145e4e089" Class="Contoso.Scripts" Function="CalculateValue" AssemblyPath="Contoso.Scripts.dll"/>  
    ```  

     更新版本号。 如果有多个实例，使用**替换为**上**编辑**菜单。  

5.  保存该文件。  

     现在即可以用映射编辑器打开该映射。  

## <a name="see-also"></a>请参阅  
 [部署 BizTalk 应用程序的最佳做法](../core/best-practices-for-deploying-a-biztalk-application.md)   
 [Admin （BizTalk Server 示例文件夹）](../core/admin-biztalk-server-samples-folder.md)   
 [以编程方式部署和启动业务流程的新版本](../core/deploying-and-starting-a-new-version-of-an-orchestration-programmatically.md)