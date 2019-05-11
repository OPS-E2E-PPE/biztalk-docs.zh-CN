---
title: 程序集位于 GAC 中的安装 |Microsoft Docs
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
ms.openlocfilehash: 6d59825ae6ee7d9fd93111580a61ed670d86b95e
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65528893"
---
# <a name="assembly-installation-in-the-gac"></a>程序集安装在 GAC 中
每台计算机包含包含由该计算机上的一个或多个应用程序使用的程序集的全局程序集缓存 (GAC)。 有关[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]若要在运行时处理消息，BizTalk 应用程序中包含的程序集必须位于运行应用程序的计算机的 Gac 中。  
  
 如果你的应用程序隔离到一台服务器，然后程序集只需要该服务器上的 GAC 中。 但是如果多个服务器承载应用程序，该应用程序中的程序集必须在需要在程序集中所含项目的访问权限的每台计算机的 GAC 中存在。 例如，如果将 Assembly_A 部署到 Server_1，然后在服务器 2 上的主机中登记 Assembly_A，必须在 Server_2 的 GAC 中安装 Assembly_A。 如果不是这样，Server_2 将无法在运行时访问 Assembly_A。  
  
 具体而言，始终必须在运行该业务流程绑定到主机的实例的服务器上的 GAC 中安装包含业务流程和它们所依赖的任何程序集的程序集。 此外，必须在运行作为端口的适配器处理程序主机的实例的服务器上安装包含的映射和管道供某端口使用的程序集。  
  
 可以指定要在部署中的程序集时在 GAC 中安装每个程序集的部署选项[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]。 或者，您可以将程序集安装到 GAC 中手动。 此外，您可以指定部署选项部署到 BizTalk 应用程序后，将程序集安装到 GAC 中。  
  
 下面汇总的工具和方法可用于将程序集安装到 GAC 中：  
  
- **Microsoft Visual Studio.** 正如前面提到，可以设置项目属性以程序集在 GAC 中自动部署时将安装它们，如中所述[如何在 Visual Studio 中设置部署属性](../core/how-to-set-deployment-properties-in-visual-studio.md)。 您还可以手动安装的程序集在 GAC 中通过使用附带的 Gacutil 命令行工具[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，如中所述[如何将程序集安装到 GAC 中](../core/how-to-install-an-assembly-in-the-gac.md)。  
  
- **BTSTask 命令行工具。** 使用 BTSTask 将程序集添加到 BizTalk 应用程序时可以指定选项导入或安装包含它的应用程序时，将程序集安装到 GAC 中。 有关详细信息，请参阅[AddResource 命令：BizTalk 程序集](../core/addresource-command-biztalk-assembly.md)。 另请参阅[AddResource 命令：.NET 程序集](../core/addresource-command-net-assembly.md)。  
  
- **BizTalk Server 管理控制台。** 在与 BTSTask 相同的方式，当你通过使用管理控制台中，向应用程序添加程序集时可以指定选项导入或安装包含它的应用程序时，将程序集安装到 GAC 中。 有关详细信息，请参阅[如何将 BizTalk 程序集添加到应用程序](../core/how-to-add-a-biztalk-assembly-to-an-application.md)。 另请参阅[如何将.NET 程序集添加到应用程序](../core/how-to-add-a-net-assembly-to-an-application.md)。  
  
   此外，你可以配置部署选项在任何时间之后部署程序集或将其添加到应用程序，如中所述[如何修改 BizTalk 程序集的部署选项](../core/how-to-modify-the-deployment-options-of-a-biztalk-assembly.md)。 当将程序集部署到[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]从[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]第一次，在管理控制台中的部署选项设置，如下所示：安装上的 GAC 启用和禁用关于导入的 gac。 如果更改这些设置时，所做的更改仍将有效从重新部署程序集如果[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]。  
  
- **拖放。** 使用 Windows 资源管理器，可以将拖放到的程序集文件\< *Windows 文件夹*\>\assembly。  
  
- **其他方法。** 有其他工具和方法，包括使用 Windows 安装程序或由第三方供应商创建的工具将程序集安装到 GAC 中。  
  
> [!IMPORTANT]
>  以便你的应用程序正常工作，请确保程序集的相同版本并在 BizTalk 管理数据库和 GAC 中。 如果您做不始终将程序集安装到 GAC 中时将其部署，您可能必须在 GAC 和 BizTalk 管理数据库，这将导致在运行时处理错误的不同版本。  
> 
> [!IMPORTANT]
>  有关版本编号的信息，请参阅"程序集版本控制"可从 Microsoft.NET Framework 帮助中[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]。 请注意，不支持使用.NET 策略文件[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。  
  
## <a name="see-also"></a>请参阅  
 [部署 BizTalk 程序集从 Visual Studio 到 BizTalk 应用程序](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)   
 [了解 BizTalk 应用程序的部署和管理](../core/understanding-biztalk-application-deployment-and-management.md)