---
title: 如何重新部署 BizTalk 程序集从 Visual Studio |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5c4bb627-48de-4874-bb25-af2c513dbc51
caps.latest.revision: 41
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 68a3d764a02063253e889498e21c65d602973fd9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37008854"
---
# <a name="how-to-redeploy-a-biztalk-assembly-from-visual-studio"></a>如何从 Visual Studio 重新部署 BizTalk 程序集
在开发程序集的过程中，你通常需要重复地部署、测试、修改以及重新部署该程序集。 在以前版本的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中，如果你希望在不更改版本号的情况下重新部署程序集，则首先需要手动停止、取消登记和取消绑定包含在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 程序集中的项目，然后从 BizTalk 管理（配置）数据库中删除该程序集。 此外，在重新部署程序集后，还需要在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中绑定、登记和启动程序集的项目。  
  
 使用 BizTalk Server，但是，当你启用中的重新部署选项[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]自动执行所有步骤才能重新部署程序集所需执行。 尽管可以从项目级重新部署某个程序集（如在解决方案资源管理器中右键单击该项目，然后单击“部署”），但我们强烈建议你始终从解决方案级重新部署程序集（如通过右键单击该解决方案，然后单击“部署”）。 后面的方法将立即重新部署解决方案中的所有程序集，并处理具有依赖项时涉及到的所有步骤（在后面介绍）。  
  
> [!IMPORTANT]
>  虽然需要在项目级重新部署的情况少之又少，但一般情况下，你应始终在解决方案级重新部署。  
  
 在重新部署程序集时，请切记以下几点重要事项：  
  
- **必须在 GAC 中安装新程序集。** 时重新部署程序集，您必须始终安装新版本的程序集在 GAC 中，如中所述[如何将程序集安装到 GAC 中](../core/how-to-install-an-assembly-in-the-gac.md)。 重新部署程序集后可实现此目的。  
  
- **您应始终重新部署解决方案级别时存在一些依赖关系。** 如果解决方案中有多个程序集，并且解决方案中的一个或多个程序集对要重新部署的程序集具有依存关系，则应在解决方案级重新部署程序集。 这是因为重新部署项目级别的程序集时[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将停止、 取消登记、 取消绑定，并依赖于此程序集时此程序集所依赖的所有程序集中删除项目。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 将不会部署、 绑定、 登记和启动这些项目的其他步骤。 但是，在重新部署整个解决方案时，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 将根据解决方案中所有项目的依存关系，自动执行所需步骤来取消部署和重新部署这些项目。  
  
- **您可能需要手动重新部署依存程序集。** [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 通常取消部署依存程序集，但在以下情况下，您必须执行附加步骤以部署、 绑定和登记中每个依赖程序集后重新部署程序集所依赖的程序集的项目：  
  
  - 在项目级重新部署了某个程序集，同一解决方案中的另一个程序集依赖于此程序集。  
  
  - 在解决方案级重新部署了某个程序集，但依存程序集存在于其他解决方案中。  
  
    例如，如果仅需要重新部署下图中的程序集 3，则重新部署之后需要部署、绑定和登记程序集 2 中的项目，然后部署、绑定和登记程序集 1 中的项目。  
  
    ![程序集具有依赖项](../core/media/assemblydependencies.gif "AssemblyDependencies")  
  
    另一种方法是避免未更改核心程序集的不必要部署。  以上图为例，如果存在其他依赖程序集 2 和程序集 3 的程序集，且这些程序集都没有进行更新，  取消选中**部署**在 configuration manager 中为程序集 2 和程序集 3 项目的选项。 这样，依赖它们的外部程序集在需要重新部署时将不会被取消部署。 有关详细信息，请参阅[如何在 Visual Studio 中设置部署属性](../core/how-to-set-deployment-properties-in-visual-studio.md)。  
  
- **您必须重新启动主机实例。** 在不更改程序集版本号的情况下重新部署包含业务流程的程序集时，BizTalk 管理数据库中的现有程序集将被覆盖。 不过，在更改生效之前，必须重新启动该业务流程绑定到的主机的所有主机实例。 你可以指定在重新部署程序集时自动重新启动本地计算机上的所有主机实例。 有关说明，请参阅[如何在 Visual Studio 中设置部署属性](../core/how-to-set-deployment-properties-in-visual-studio.md)。 您可以手动停止和启动每个主机实例，如中所述[如何停止主机实例](../core/how-to-stop-a-host-instance.md)并[如何启动主机实例](../core/how-to-start-a-host-instance.md)。  
  
> [!IMPORTANT]
>  因为重新部署选项绕过版本控制，我们建议使用仅在开发过程。  
  
## <a name="prerequisites"></a>必要條件  
 若要执行本主题中的步骤，你必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators 组成员的帐户身份登录。 此外，你的帐户还必须对本地文件系统和全局程序集缓存 (GAC) 具有读写权限。 本地计算机的管理员帐户拥有这些权限。  
  
## <a name="to-redeploy-a-biztalk-solution"></a>重新部署 BizTalk 解决方案  
  
#### <a name="using-visual-studio-solution-explorer"></a>使用 Visual Studio 解决方案资源管理器  
  
1. 确保在解决方案中，每个项目的部署属性中启用重新部署选项中所述[如何在 Visual Studio 中设置部署属性](../core/how-to-set-deployment-properties-in-visual-studio.md)。 默认情况下该选项处于启用状态。  
  
2. 在中[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]解决方案资源管理器，右键单击 BizTalk 解决方案，然后依次**部署**。  
  
    解决方案中的程序集将部署到指定的 BizTalk 应用程序中。 生成和部署过程的状态显示在该页的左下角中。  
  
#### <a name="using-the-visual-studio-command-prompt"></a>使用 Visual Studio 命令提示  
  
1.  确保在解决方案中，每个项目的部署属性中启用重新部署选项中所述[如何在 Visual Studio 中设置部署属性](../core/how-to-set-deployment-properties-in-visual-studio.md)。 默认情况下该选项处于启用状态。  
  
2.  启动**Visual Studio 命令提示符**。  
  
3.  键入以下命令，替换适当的值下, 表中所述：  
  
     **devenv /deploy***SolnConfigName* *解决方案名称*   
  
     例如：  
  
     **devenv / 部署版本"C:\Documents 和 Settings\someuser\My Documents\Visual Studio\Projects\MySolution\MySolution.sln"**  
  
    |参数|ReplTest1|  
    |---------------|-----------|  
    |**/ 部署**|生成或重新生成后部署解决方案。|  
    |*SolnConfigName*|用于生成 SolutionName 中指定的解决方案的解决方案配置的名称。|  
    |*解决方案名称*|解决方案文件的完整路径和名称。|  
  
## <a name="see-also"></a>请参阅  
 [将 BizTalk 程序集从 Visual Studio 部署到 BizTalk 应用程序](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)