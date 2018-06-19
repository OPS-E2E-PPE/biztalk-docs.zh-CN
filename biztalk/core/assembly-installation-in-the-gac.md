---
title: 程序集安装在 gac 中 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3b12d00c-8750-4c6d-8244-e613f955a478
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 25af22c85602c323b87340cce8b740fe5b68accb
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25966403"
---
# <a name="assembly-installation-in-the-gac"></a>程序集安装在 gac 中
每台计算机都包含全局程序集缓存 (GAC)，其中包含该计算机上的一个或多个应用程序所使用的程序集。 为使 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 能够在运行时处理消息，BizTalk 应用程序中包括的程序集必须位于运行该应用程序的计算机的 GAC 中。  
  
 如果您的应用程序单独放置在一台服务器上，则程序集只需位于该服务器的 GAC 中。 不过，如果该应用程序有多个宿主服务器，那么该应用程序中的程序集必须位于需要访问程序集所含项目的所有计算机的 GAC 中。 例如，如果将 Assembly_A 部署到 Server_1，，然后在服务器 2 上的主机中登记 Assembly_A Assembly_A 必须安装在服务器 2 上的 GAC 中。 如果不是这样，服务器 2 不能在运行时访问 Assembly_A。  
  
 特别是，如果程序集包含业务流程以及它们所依赖的任何程序集，则必须始终在运行特定主机（与业务流程绑定）实例的服务器的 GAC 中安装这些程序集。 此外，如果程序集包含供某端口使用的映射和管道，则必须在运行特定主机（充当该端口的适配器处理程序）实例的服务器上安装这些程序集。  
  
 您可以为各个程序集指定部署选项，在从 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 部署程序集时将其安装到 GAC 中。 或者，也可以将程序集手动安装到 GAC 中。 此外，您可以指定部署选项，在将程序集部署到 BizTalk 应用程序中后将该程序集安装到 GAC 中。  
  
 下文汇总了将程序集安装到 GAC 中时可供使用的工具和方法：  
  
-   **Microsoft Visual Studio。** 如前所述，你可以设置项目属性以程序集在 GAC 中自动安装时将它们，部署中所述[如何在 Visual Studio 中设置部署属性](../core/how-to-set-deployment-properties-in-visual-studio.md)。 你还可以手动安装的程序集在 GAC 中使用 Gacutil 命令行工具附带[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]中所述，[如何将程序集安装在 GAC 中](../core/how-to-install-an-assembly-in-the-gac.md)。  
  
-   **BTSTask 命令行工具。** 使用 BTSTask 向 BizTalk 应用程序添加程序集后，可以指定选项，在导入或安装包含该程序集的应用程序时将该程序集安装到 GAC 中。 有关详细信息，请参阅[AddResource 命令： BizTalk 程序集](../core/addresource-command-biztalk-assembly.md)。 另请参阅[AddResource 命令：.NET 程序集](../core/addresource-command-net-assembly.md)。  
  
-   **BizTalk Server 管理控制台。** 与 BTSTask 的方式相同，使用管理控制台向某个应用程序添加程序集后，可以指定选项，在导入或安装包含该程序集的应用程序时将该程序集安装到 GAC 中。 有关详细信息，请参阅[如何将 BizTalk 程序集添加到应用程序](../core/how-to-add-a-biztalk-assembly-to-an-application.md)。 另请参阅[如何将.NET 程序集添加到应用程序](../core/how-to-add-a-net-assembly-to-an-application.md)。  
  
     此外，你可以配置部署选项在任何时间之后部署到程序集或将其添加到应用程序中所述[如何修改 BizTalk 程序集的部署选项](../core/how-to-modify-the-deployment-options-of-a-biztalk-assembly.md)。 当将程序集部署到[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]从[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]第一次，在管理控制台中的部署选项设置，如下所示： 启用 GAC 上安装并导入 GAC 已禁用。 如果对这些设置进行更改，所做的更改仍将有效如果程序集从重新部署[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]。  
  
-   **拖放。** 使用 Windows 资源管理器，你可以拖放到的程序集文件\< *Windows 文件夹*\>\assembly。  
  
-   **其他方法。** 还可以选择其他工具和方法，包括使用 Windows Installer 或第三方厂商开发的工具，将程序集安装到 GAC 中。  
  
> [!IMPORTANT]
>  为使您的应用程序正常工作，应确保 BizTalk 管理数据库和 GAC 中的程序集具有相同版本。 如果部署程序集时并不总是将其安装到 GAC 中，GAC 和 BizTalk 管理数据库中的程序集版本可能有所不同，从而导致运行时出现处理错误。  
  
> [!IMPORTANT]
>  有关版本编号的信息，请参阅 Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 提供的 .NET Framework 帮助中的“程序集版本控制”。 请注意，不支持的.NET 策略文件的使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。  
  
## <a name="see-also"></a>另请参阅  
 [部署到 BizTalk 应用程序从 Visual Studio BizTalk 程序集](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)   
 [了解 BizTalk 应用程序的部署和管理](../core/understanding-biztalk-application-deployment-and-management.md)