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
ms.openlocfilehash: 5500411803bc63d2af0b1196ada2dd6dacc1f7f0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65384420"
---
# <a name="how-to-redeploy-a-biztalk-assembly-from-visual-studio"></a>如何重新部署 BizTalk 程序集从 Visual Studio
在开发程序集，过程中您通常需要部署，测试、 修改和重新部署它重复。 在旧版[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，如果你想要重新部署程序集，而无需更改的版本编号，首先需要手动停止、 取消登记和取消绑定中的程序集所含项目[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，然后删除中的程序集BizTalk 管理 （配置） 数据库。 此外，在重新部署程序集之后, 您需要将绑定、 登记并启动其项目中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。  
  
 使用 BizTalk Server，但是，当你启用中的重新部署选项[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]自动执行所有步骤才能重新部署程序集所需执行。 尽管您可以重新部署项目级别中的程序集 (如通过右键单击解决方案资源管理器中的项目并单击部署) 来重新部署单独的程序集，我们强烈建议你始终重新部署程序集的解决方案级别 （从例如，通过右键单击解决方案并单击部署）。 这次重新部署所有解决方案中的程序集，并处理所有所涉及的步骤时存在一些依赖关系，如下文所述。  
  
> [!IMPORTANT]
>  虽然有极少数情况下，您可能需要在项目级重新部署，但通常您应始终重新部署解决方案级别。  
  
 当重新部署程序集，请记住以下重要事项：  
  
- **必须在 GAC 中安装新程序集。** 时重新部署程序集，您必须始终安装新版本的程序集在 GAC 中，如中所述[如何将程序集安装到 GAC 中](../core/how-to-install-an-assembly-in-the-gac.md)。 重新部署它后，你可以执行此操作。  
  
- **您应始终重新部署解决方案级别时存在一些依赖关系。** 如果在解决方案中，有多个程序集并在解决方案中的一个或多个程序集具有你想要重新部署的程序集的依赖项，则应重新部署您在解决方案级别的程序集。 这是因为重新部署项目级别的程序集时[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将停止、 取消登记、 取消绑定，并依赖于此程序集时此程序集所依赖的所有程序集中删除项目。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 将不会部署、 绑定、 登记和启动这些项目的其他步骤。 但是，重新部署整个解决方案时[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]会自动将带取消部署和重新部署所有基于及其依赖项的解决方案中的项目所需的步骤。  
  
- **您可能需要手动重新部署依存程序集。** [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 通常取消部署依存程序集，但在以下情况下，您必须执行附加步骤以部署、 绑定和登记中每个依赖程序集后重新部署程序集所依赖的程序集的项目：  
  
  - 如果重新部署项目级别的程序集，并且在同一解决方案中的另一个程序集依赖于它。  
  
  - 如果重新部署程序集级别的解决方案，但依赖程序集存在于另一种解决方案。  
  
    例如，如果您打算重新部署仅在下图中所示的程序集 3，需要部署，请重新绑定，请和登记程序集 2 中的项目部署、 绑定，并登记程序集 1 中的项目。  
  
    ![程序集具有依赖项](../core/media/assemblydependencies.gif "AssemblyDependencies")  
  
    另一种方法是避免不必要的核心程序集未更改的部署。  例如在关系图中更高版本，如果有其他程序集依赖于程序集 2 和程序集 3，而这些程序集都已更新。  取消选中**部署**在 configuration manager 中为程序集 2 和程序集 3 项目的选项。 这种方式，依赖它们的外部程序集不会取消部署需重新部署即可。 有关详细信息，请参阅[如何在 Visual Studio 中设置部署属性](../core/how-to-set-deployment-properties-in-visual-studio.md)。  
  
- **您必须重新启动主机实例。** 重新部署包含业务流程，而无需更改程序集版本号的程序集时，现有程序集将在 BizTalk 管理数据库中被覆盖。 此更改将生效之前，但是，必须重新启动该业务流程绑定到主机的每个主机实例。 可以指定本地计算机上的所有主机实例时自动重新都启动重新部署程序集的选项。 有关说明，请参阅[如何在 Visual Studio 中设置部署属性](../core/how-to-set-deployment-properties-in-visual-studio.md)。 您可以手动停止和启动每个主机实例，如中所述[如何停止主机实例](../core/how-to-stop-a-host-instance.md)并[如何启动主机实例](../core/how-to-start-a-host-instance.md)。  
  
> [!IMPORTANT]
>  因为重新部署选项绕过版本控制，我们建议使用仅在开发过程。  
  
## <a name="prerequisites"></a>先决条件  
 若要执行本主题中的过程，您必须登录的成员帐户[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Administrators 组。 此外，你的帐户必须具有对本地文件系统和全局程序集缓存 (GAC) 的读/写权限。 在本地计算机上的管理员帐户拥有这些权限。  
  
## <a name="to-redeploy-a-biztalk-solution"></a>若要重新部署 BizTalk 解决方案  
  
#### <a name="using-visual-studio-solution-explorer"></a>使用 Visual Studio 解决方案资源管理器  
  
1. 确保在解决方案中，每个项目的部署属性中启用重新部署选项中所述[如何在 Visual Studio 中设置部署属性](../core/how-to-set-deployment-properties-in-visual-studio.md)。 默认情况下启用此选项。  
  
2. 在中[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]解决方案资源管理器，右键单击 BizTalk 解决方案，然后依次**部署**。  
  
    在解决方案中的程序集将部署到指定的 BizTalk 应用程序。 生成和部署过程中显示的页面的左下角的状态。  
  
#### <a name="using-the-visual-studio-command-prompt"></a>使用 Visual Studio 命令提示  
  
1.  确保在解决方案中，每个项目的部署属性中启用重新部署选项中所述[如何在 Visual Studio 中设置部署属性](../core/how-to-set-deployment-properties-in-visual-studio.md)。 默认情况下启用此选项。  
  
2.  启动**Visual Studio 命令提示符**。  
  
3.  键入以下命令，替换适当的值下, 表中所述：  
  
     **devenv /deploy**  *SolnConfigName* *SolutionName*  
  
     例如：  
  
     **devenv /deploy Release "C:\Documents and Settings\someuser\My Documents\Visual Studio\Projects\MySolution\MySolution.sln"**  
  
    |参数|ReplTest1|  
    |---------------|-----------|  
    |**/deploy**|生成或重新生成后部署解决方案。|  
    |*SolnConfigName*|将用于生成 SolutionName 中命名的解决方案的解决方案配置的名称。|  
    |*SolutionName*|完整路径和解决方案文件的名称。|  
  
## <a name="see-also"></a>请参阅  
 [将 BizTalk 程序集从 Visual Studio 部署到 BizTalk 应用程序](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)