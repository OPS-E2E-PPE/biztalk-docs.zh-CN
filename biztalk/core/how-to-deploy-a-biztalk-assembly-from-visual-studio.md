---
title: 如何部署 BizTalk 程序集从 Visual Studio |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 69d70c52-3e71-4eb2-876e-b467c7ca24b7
caps.latest.revision: 39
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c5a84479d6717ebe27614243f503cabd66866926
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385311"
---
# <a name="how-to-deploy-a-biztalk-assembly-from-visual-studio"></a>如何部署 BizTalk 程序集从 Visual Studio
本主题说明了使用[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]解决方案资源管理器或[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]命令提示符下，若要部署 BizTalk 程序集从[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]到 BizTalk 应用程序。 虽然可以将部署从项目级别的单个程序集 (如通过右键单击该项目并单击部署) 也部署在一次从解决方案级解决方案中的程序集的所有 (如通过右键单击解决方案并单击部署)，我们强烈建议在一次从解决方案级的程序集的所有部署。  
  
 与以前版本的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，如果你想要部署多个程序集在解决方案中，并且任何程序集依赖于任何其他程序集，则必须单独部署的程序集及其依赖关系的相反的顺序。 例如，如果 assembly1 依赖于 Assembly2，你必须先部署 Assembly2，，然后才能部署 Assembly1。  
  
 在部署中的项目级别的程序集时，这仍然是这种情况。 使用 BizTalk Server，但是，当部署程序集从解决方案级而不是项目级[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]自动处理好所有的部署步骤，包括按正确的顺序部署程序集。 因此，为了简化部署，另一个程序集上部署的程序集没有依赖关系时，应部署您在解决方案级别的程序集。  
  
 当你选择部署项目或解决方案中的选项[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，程序集或程序集是自动生成并部署到本地 BizTalk 组中指定的 BizTalk 应用程序。 如果组中不存在该应用程序，部署也会创建应用程序。 注册程序集和它们所包含的项目和其数据存储在 BizTalk 组的 BizTalk 管理 （配置） 数据库。 此外，如果该项目的部署属性中指定此选项，程序集都添加到全局程序集缓存 (GAC)。  
  
 "项目"是 BizTalk 应用程序，包括在中使用的资源中包含的任何项[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，如程序集和业务流程，以及创建或部署该应用程序后稍后再添加其他项如发送和接收端口，证书和脚本。 部署程序集后，可以查看并管理其项目中的应用程序节点[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]控制台。 每个应用程序其子文件夹显示在应用程序中的项目存储在其自己的文件夹中。 有关详细信息，请参阅[使用 BizTalk Server 管理控制台](../core/using-the-biztalk-server-administration-console.md)。 有关创建和管理应用程序的详细信息，请参阅[部署和管理 BizTalk 应用程序](../core/deploying-and-managing-biztalk-applications.md)。  
  
 在部署程序集之前，必须执行以下步骤：  
  
-   创建强名称程序集密钥文件并将其分配到每个项目，如中所述[如何配置强名称程序集密钥文件](../core/how-to-configure-a-strong-name-assembly-key-file.md)。  
  
-   设置为项目部署属性，如中所述[如何在 Visual Studio 中设置部署属性](../core/how-to-set-deployment-properties-in-visual-studio.md)。  
  
-   如果之前已部署程序集，使项目重新部署选项。 有关说明和重新部署的其他重要信息，请参阅[如何重新部署 BizTalk 程序集从 Visual Studio](../core/how-to-redeploy-a-biztalk-assembly-from-visual-studio.md)。  
  
> [!IMPORTANT]
>  永远不应执行本主题中所述，在生产计算机上的任务。 在开发过程中，开发人员经常需要重新部署程序集从[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]。 若要启用重新部署，[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]可能取消部署、 取消绑定、 停止和取消登记在相同或不同应用程序中存在的项目。 虽然这是必要和适当的开发环境中，它可能会导致意外后果导致生产环境中。 此外，为了避免有人尝试从部署程序集[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]的生产计算机上，我们建议您不要安装[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]的生产计算机上。  
> 
> [!NOTE]
>  .NET framework 运行时安全策略可防止部署默认情况下在网络中的程序集共享。 如果你尝试从网络共享部署程序集并遇到困难，请参阅.NET Framework 安全管理员，或请参阅"安全策略管理"中[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]组合集。  
  
## <a name="prerequisites"></a>先决条件  
 若要执行本主题中的过程，你必须登录的成员帐户[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Administrators 组。 如果在**部署**属性，您已经启用了选项后，将程序集安装到全局程序集缓存 (GAC) 中，则你还需要 GAC 上的读/写权限。 在本地计算机上的管理员帐户拥有此权限。 有关详细的权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。  
  
## <a name="to-deploy-a-biztalk-assembly-or-assemblies"></a>若要部署的 BizTalk 程序集或程序集  
  
#### <a name="using-visual-studio-solution-explorer"></a>使用 Visual Studio 解决方案资源管理器  
  
- 在中[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]解决方案资源管理器，右键单击 BizTalk 项目或解决方案，然后依次**部署**。  
  
   在项目中的程序集或解决方案中的程序集将部署到指定的 BizTalk 应用程序。 生成和部署过程中显示的页面的左下角的状态。  
  
#### <a name="using-the-visual-studio-command-prompt"></a>使用 Visual Studio 命令提示  
  
1.  启动**Visual Studio 命令提示符**。  
  
2.  键入以下命令，替换适当的值下, 表中所述：  
  
     **devenv /deploy**  *SolnConfigName* *SolutionName* [**/project** *ProjName*] [**/projectconfig** *ProjConfigName*]  
  
     例如：  
  
     **devenv /deploy Release "C:\Documents and Settings\someuser\My Documents\Visual Studio\Projects\MySolution\MySolution.sln" /project "MyBizTalkApp\MyBizTalkApp.csproj" projectconfig Release**  
  
    |参数|ReplTest1|  
    |---------------|-----------|  
    |**/deploy**|生成或重新生成后部署解决方案。|  
    |*SolnConfigName*|将用于生成 SolutionName 中命名的解决方案的解决方案配置的名称。|  
    |*SolutionName*|完整路径和解决方案文件的名称。|  
    |**/project**  *ProjName*|路径和解决方案中的项目文件的名称。 您可以输入相对路径从 SolutionName 文件夹到项目文件中，或项目的显示名称或完整路径和项目文件的名称。|  
    |**/projectconfig**  *ProjConfigName*|生成配置生成项目时要使用的项目名称。|  
  
     首次部署包含业务流程的程序集可能会收到一条警告消息，业务流程未包含在绑定文件。 这是因为业务流程没有自动绑定到在部署后的主机。 必须手动执行此步骤。  
  
## <a name="see-also"></a>请参阅  
 [将 BizTalk 程序集从 Visual Studio 部署到 BizTalk 应用程序](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)