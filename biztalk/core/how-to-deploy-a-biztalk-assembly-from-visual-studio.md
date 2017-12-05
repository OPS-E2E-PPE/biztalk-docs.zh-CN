---
title: "如何部署 BizTalk 程序集，从 Visual Studio |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 69d70c52-3e71-4eb2-876e-b467c7ca24b7
caps.latest.revision: "39"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8fc232edf6d99e31b5679932eb19873481fa579b
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
---
# <a name="how-to-deploy-a-biztalk-assembly-from-visual-studio"></a>如何从 Visual Studio 部署 BizTalk 程序集
本主题说明了使用[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]解决方案资源管理器或[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]命令提示符下，部署将 BizTalk 的程序集[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]到 BizTalk 应用程序。 尽管可以从项目级部署单个程序集（如右键单击项目，然后单击“部署”），也可以从解决方案级一次部署解决方案中的所有程序集（如右键单击解决方案，然后单击“部署”），但我们强烈建议你从解决方案级一次部署所有程序集。  
  
 对于早期版本的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，如果你需要部署解决方案中的多个程序集，并且解决方案中的任一程序集依赖于其他程序集中的任何一个，则必须按照其依赖关系的相反顺序分别部署程序集。 例如，如果 Assembly1 依赖于 Assembly2，则必须先部署 Assembly2，然后才能部署 Assembly1。  
  
 从项目级部署程序集时也是这样。 与 BizTalk Server 中，但是，当你部署的解决方案级别而不是项目级别中的程序集[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]会自动负责所有的部署步骤，包括部署中正确的顺序的程序集。 因此，为了简化部署，如果另一个程序集依赖于你要部署的程序集，则应该在解决方案级部署程序集。  
  
 当你选择了从 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 部署项目或解决方案的选项后，会生成一个或多个程序集，并部署到本地 BizTalk 组中的指定 BizTalk 应用程序中。 如果该应用程序在组中不存在，则部署操作也会创建该应用程序。 程序集及其包含的项目将被注册，并且其数据存储在 BizTalk 组的 BizTalk 管理（配置）数据库中。 此外，如果在项目的部署属性中指定此选项，程序集将被添加到全局程序集缓存 (GAC)。  
  
 “项目”是 BizTalk 应用程序中包括的任何项，包括你在 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 中使用的资源，如程序集、业务流程以及你在部署应用程序后稍后再创建或添加的其他项，如发送端口和接收端口、证书和脚本。 在部署程序集后，你可以在 [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)] 控制台的“应用程序”节点中查看和管理其项目。 每个应用程序存储在自己的文件夹中，其子文件夹显示应用程序中的项目。 有关详细信息，请参阅[使用 BizTalk Server 管理控制台](../core/using-the-biztalk-server-administration-console.md)。 有关创建和管理应用程序的详细信息，请参阅[部署和管理 BizTalk 应用程序](../core/deploying-and-managing-biztalk-applications.md)。  
  
 部署程序集之前，必须执行以下步骤：  
  
-   创建强名称程序集密钥文件并将其分配给每个项目中所述[如何配置一个强名称程序集密钥文件](../core/how-to-configure-a-strong-name-assembly-key-file.md)。  
  
-   设置为项目的部署属性中所述[如何在 Visual Studio 中设置部署属性](../core/how-to-set-deployment-properties-in-visual-studio.md)。  
  
-   如果以前已部署了程序集，请为项目启用重新部署选项。 有关说明以及有关重新部署的其他重要信息，请参阅[如何重新部署 BizTalk 程序集从 Visual Studio](../core/how-to-redeploy-a-biztalk-assembly-from-visual-studio.md)。  
  
> [!IMPORTANT]
>  勿在生产计算机上执行本主题中说明的任务。 在开发过程中，开发人员经常需要重新部署 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 中的程序集。 为了进行重新部署，[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 会对相同或不同应用程序中存在的项目取消部署、取消绑定、停止并取消登记。 虽然在部署环境中这样做是必要和适当的，但在生产环境中会产生意外和不需要的结果。 另外，为了避免有人尝试在生产计算机上部署 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 中的程序集，建议你不要在生产计算机上安装 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]。  
  
> [!NOTE]
>  默认情况下，.NET Framework 运行时安全策略可防止从网络共享部署程序集。 如果你尝试从网络共享部署程序集并遇到困难，请与 .NET Framework 安全管理员联系，或者参阅 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 联合帮助集中的“Security Policy Management”（安全策略管理）。  
  
## <a name="prerequisites"></a>先决条件  
 为了执行本主题中的过程，你必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators 组成员的帐户登录。 如果是，在**部署**属性，你已启用了选项，将程序集安装到全局程序集缓存 (GAC) 中，则你还需要在 gac 中的读/写权限。 本地计算机的管理员帐户拥有此权限。 有关更多详细权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。  
  
## <a name="to-deploy-a-biztalk-assembly-or-assemblies"></a>部署一个或多个 BizTalk 程序集  
  
#### <a name="using-visual-studio-solution-explorer"></a>使用 Visual Studio 解决方案资源管理器  
  
-   在[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]解决方案资源管理器，右键单击 BizTalk 项目或解决方案中，然后单击**部署**。  
  
     项目中的程序集或解决方案中的程序集将部署到指定的 BizTalk 应用程序中。 生成和部署过程的状态显示在该页的左下角中。  
  
#### <a name="using-the-visual-studio-command-prompt"></a>使用 Visual Studio 命令提示  
  
1.  启动**Visual Studio 命令提示**。  
  
2.  键入以下命令，替换为适当的值下, 表中所述：  
  
     **devenv / 部署***SolnConfigName* *SolutionName* [**/项目** *ProjName*] [**/projectconfig** *ProjConfigName*]  
  
     例如：  
  
     **devenv / 部署"C:\Documents 和 Settings\someuser\My Documents\Visual Studio\Projects\MySolution\MySolution.sln"版本 / 项目"MyBizTalkApp\MyBizTalkApp.csproj"projectconfig 版本**  
  
    |参数|值|  
    |---------------|-----------|  
    |**/ 部署**|生成或重新生成后部署解决方案。|  
    |*SolnConfigName*|用于生成 SolutionName 中指定的解决方案的解决方案配置的名称。|  
    |*解决方案名称*|解决方案文件的完整路径和名称。|  
    |**/ 项目***ProjName* |解决方案内的项目文件的路径和名称。 可以输入从 SolutionName 文件夹到项目文件的相对路径、项目的显示名称或项目文件的完整路径和名称。|  
    |**/projectconfig***ProjConfigName* |在生成项目时要使用的项目生成配置的名称。|  
  
     第一次部署包含业务流程的程序集时，可能收到通知你绑定文件中不包含该业务流程的警告消息。 这是因为在部署后业务流程没有自动绑定到主机。 你必须手动执行此步骤。  
  
## <a name="see-also"></a>另请参阅  
 [将 BizTalk 程序集从 Visual Studio 部署到 BizTalk 应用程序](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)