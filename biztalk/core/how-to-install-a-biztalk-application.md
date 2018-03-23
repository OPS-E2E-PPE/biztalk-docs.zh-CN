---
title: 如何安装 BizTalk 应用程序 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- installing, requirements
- installing, applications
- installing, warnings
- applications, installing
ms.assetid: 99ee0b1a-d46a-4fb6-802b-6827dc740418
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ffc3d1d6d8fdbfcc168446883e2b65a7d8ed0351
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2018
---
# <a name="how-to-install-a-biztalk-application"></a>如何安装 BizTalk 应用程序
本主题介绍如何通过在 Windows 界面中双击应用程序的 Windows Installer (.msi) 文件或从命令行运行 msiexec 来在本地计算机上安装应用程序。 你也可以启动安装向导导入向导的最后一步骤中所述[如何导入 BizTalk 应用程序](../core/how-to-import-a-biztalk-application.md)。  
  
> [!CAUTION]
>  如果计算机上已安装了该应用程序，则可以选择修复该应用程序。 仅在已为应用程序安装了单个 .msi 时才支持修复功能。 如果已在计算机上为该应用程序安装了多个 .msi，则不应该选择此选项。 这是因为选择“修复”会撤消在安装此 .msi 文件之后安装的其他 .msi 文件所进行的修改，从而导致应用程序故障。  
  
 只有在将应用程序安装在运行该应用程序的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 计算机上，才能运行该应用程序。 安装应用程序时会将其资源放在本地文件系统中。 根据应用程序、其内容和配置的不同，安装还可能进行以下操作：  
  
-   将程序集添加到全局程序集缓存 (GAC)  
  
-   安装证书和虚拟目录  
  
-   将组件添加到 Windows 注册表。  
  
-   运行预处理或后处理脚本（如果在 .msi 文件中存在）。  
  
 有关背景信息，请参阅[会发生什么情况项目期间安装和卸载](../core/what-happens-to-artifacts-during-installation-and-uninstallation.md)。  
  
## <a name="prerequisites"></a>先决条件  
 若要执行本主题中所述的过程，必须用在本地文件系统上具有写权限的帐户进行登录。 根据应用程序中所包括的项目，可能还需要对 Windows 注册表、GAC、证书存储和 Internet 信息服务拥有写权限。 本地计算机的管理员帐户拥有这些权限。 有关更多详细权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。  
  
## <a name="considerations-for-installing-an-application"></a>安装应用程序的注意事项  
 在安装应用程序时，可能适用以下注意事项︰  
  
-   **你还必须安装此应用程序所依赖的任何应用程序。** 如果某个项目（如 BizTalk 程序集）包含在另一个应用程序中，而要安装的应用程序之该项目之间存在依存关系，则在安装该应用程序时，还必须安装包含该项目的应用程序。 可以运行应用程序之前，你必须执行此操作。 例如，如果应用程序 A 依赖于应用程序 B 中的程序集，你还必须安装应用程序 b。然后，你可以安装应用程序 a。有关背景信息，请参阅[依赖关系和应用程序部署](../core/dependencies-and-application-deployment.md)。  
  
-   **你应该停止的应用程序正在更新。** 如果要执行安装以更新应用程序中的某个项目，则除非更新中包括的程序集有一个或多个具有与现有程序集相同的版本，否则不需要停止应用程序。 在这种情况下，必须在安装更新之前停止应用程序。 不过，建议您在任何情况下都应停止应用程序，除非您知道在应用程序运行时更新不会妨碍应用程序。 有关详细信息，请参阅[更新 BizTalk 应用程序](../core/updating-biztalk-applications.md)。  
  
-   **当你安装的同一应用程序的多个.msi 文件时，没有在添加或删除程序中所做的只有一个条目。** 例如，您可以进行此操作以更新现有的应用程序。 然后，可以使用控制面板中的“添加或删除程序”来完全卸载应用程序，包括任何更新的项目。 请注意，不支持通过双击 .msi 文件或使用 msiexec 来卸载应用程序。 有关详细信息，请参阅[如何卸载 BizTalk 应用程序](../core/how-to-uninstall-a-biztalk-application.md)。  
  
-   **证书必须存在于承载发送端口之前应用程序可运行的所有计算机上。** “其他人”证书存储中包含发送端口使用的证书。  
  
-   **你可以为不同的.msi 文件，以便安装，挑选应用程序项目。** 不必在将要运行该应用程序的每台计算机上都安装所有的应用程序项目。 可以将应用程序项目的子集导出到不同的 .msi 文件中以便安装在不同的计算机上。 有关说明，请参阅[how to Export BizTalk 应用程序如何](../core/how-to-export-a-biztalk-application.md)。  
  
-   **如果应用程序.msi 文件包括虚拟目录，则必须在本地计算机上运行 Internet 信息服务 (IIS)。** 否则，安装将失败。  
  
-   **如果应用程序包括与本地计算机上已存在同名的虚拟目录，从应用程序的资源会添加到它。** 如果不同名，则会创建该虚拟目录。 任何与添加的文件同名的现有文件都将被覆盖。 另外，现有虚拟目录的安全设置不变，因此应该验证其是否足够安全。  
  
-   **在安装应用程序之前创建虚拟目录的应用程序的池。** 如果应用程序中包括虚拟目录，并且 IIS 中尚不存在应用程序池，则应在安装之前，手动创建该应用程序池。 这样，在安装过程中，虚拟目录将会绑定到该应用程序池。 如果没有创建应用程序池，则在安装时，虚拟目录将会绑定到默认的应用程序池。  
  
-   **确保 BTSHttpReceive.dll 注册为处理程序映射使用 Internet 信息服务 (IIS) 7.0。** 如果你的应用程序按顺序包含虚拟目录，用于 HTTP 接收位置工作时，必须执行此操作。  
  
-   **安装的应用程序包括在 32 位计算机上的 64 位项目时，可能会遇到问题。** 有关详细信息，请参阅[如何将一个 64 位项目添加到应用程序](../core/how-to-add-a-64-bit-artifact-to-an-application.md)。  
  
-   **如果目标目录的长度超过 260 个字符，可能会遇到问题。** 如果在安装 MSI 包过程中指定的目标目录的字符数超过 260 个字符，则安装将失败。 若要解决此问题，应确保为目标目录指定的字符数不超过 260 个字符。  
  
-   **不应该重新定位的安装文件夹。** 安装应用程序后，不应该重新定位安装文件夹或其中包含的文件。 如果这样做了，则以后尝试删除（卸载）应用程序时，删除操作将失败。 特别需要注意的是，应用程序安装文件夹中包含由 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 生成的文件，这些文件是执行删除所必需的文件。 不应该重命名、移动或删除这些文件。 文件包括︰  
  
    -   ApplicationDefinition.adf  
  
    -   Microsoft.BizTalk.CustomInstaller.dll  
  
    -   Microsoft.BizTalk.CustomInstaller.InstallState  
  
> [!NOTE]
>  如果在安装完成之前取消安装操作，则 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 将回滚安装，但在取消操作之前由预处理或后处理脚本执行的操作除外。  
  
> [!IMPORTANT]
>  在安装任何应用程序之前，请确保从可信来源获得 .msi 文件。 恶意用户可能会在 .msi 文件中包括代码，这些代码会对系统或网络造成不良影响。  有关详细信息，请参阅 [安全和 Windows Installer](../core/security-and-windows-installer.md)。  
>   
>  如果应用程序包括网站或使用 Web Services 的业务流程，则应注意，虚拟目录上的安全设置是在应用程序导出过程中生成 .msi 文件时起作用的安全设置，除非已经存在虚拟目录，此时会使用现有的设置。 安装应用程序后，应验证设置是否满足安全要求。  
>   
>  导出应用程序时，会从文件和文件夹删除 Alldiscretionary 访问控制列表 (Dacl)。 在主机实例上安装应用程序以后，必须在文件和文件夹（包括虚拟目录）上重新配置所有安全设置。  
  
-   **你可能需要更改本地路径︰ HTTP 引用的虚拟目录的指定目标计算机上创建后接收位置。**  
  
     在目标计算机上创建虚拟目录时它将指向以下物理目录之一︰  
  
     \<*安装驱动器*\>files\microsoft BizTalk Server\HttpReceive  
  
     \- **or** –  
  
     \<*安装驱动器*\>\Program 文件 (x86) \Microsoft BizTalk Server\HttpReceive  
  
     如果 BizTalk HTTP 接收 ISAPI 扩展 BTSHTTPReceive.dll 不位于指定目录中，或者目标计算机正在运行 64 位操作系统，则您必须更改虚拟目录的“本地路径：目标”，以便指向包含该 BizTalk HTTP 接收 ISAPI 扩展文件的物理目录。 例如，如果目标计算机运行 64 位版本的 Windows Vista 中，然后本地路径为： 指定的虚拟目录的内容应更改为\<安装驱动器\>\Program 文件 (x86) \Microsoft BizTalk Server\HttpReceive64。  
  
## <a name="to-install-a-biztalk-application"></a>安装 BizTalk 应用程序  
  
#### <a name="using-the-windows-interface"></a>使用 Windows 介面  
  
1.  将应用程序的 .msi 文件复制到本地计算机。  
  
2.  如果要重新安装或升级现有的 BizTalk 应用程序，并且新的安装过程中包括具有相同版本作为一个已存在于该应用程序，或与你要更新的项目进行交互的程序集，请确保应用程序已停止通过右键单击应用程序文件夹，然后单击 **停止**。  
  
3.  在 Windows 资源管理器中，双击 .msi 文件启动安装向导。  
  
4.  上 **选择安装文件夹** 页上，在 **文件夹**, ，键入 BizTalk 应用程序的完整安装路径。 示例︰ C:\Program Files\Generated BizTalk\MyApplication 通过。  
  
5.  单击 **下一步** 四次，然后在 **安装完成** 页上，单击 **关闭**。  
  
6.  如果有多台计算机将运行该应用程序，请在每台计算机上重复上述步骤。  
  
     一旦将运行它时，所有计算机上安装应用程序和应用程序已导入 BizTalk 组，你可以从应用程序[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]通过右键单击应用程序的文件夹并单击管理控制台**启动**。 有关完整说明，请参阅[如何启动和停止 BizTalk 应用程序](../core/how-to-start-and-stop-a-biztalk-application.md)。  
  
#### <a name="using-the-command-line"></a>使用命令行  
  
1.  将应用程序的 .msi 文件复制到本地计算机。  
  
2.  单击 **启动**, ，单击 **运行**, ，类型 `cmd`, ，然后按 ENTER。  
  
3.  定位到存储 .msi 文件的位置。  
  
4.  键入以下命令以安装应用程序，提供适当的参数和值下, 表中所示︰  
  
    > [!IMPORTANT]
    >  仅支持下表中显示的 msiexec 的参数。  
  
     **msiexec** [**/i**] *Package* [**/qn**] **TARGETDIR="***value***"**]  
  
     示例︰ **msiexec /i MyApplication.msi**  
  
    |参数|“值”|  
    |---------------|-----------|  
    |**/i**|安装应用程序。|  
    |*包*|Windows Installer (.msi) 文件的名称。|  
    |**/qn**|执行安装而不显示用户界面。|  
    |**TARGETDIR ="** *值* **"**|指定应用程序安装文件夹。 此值也可以在 %BTAD_InstallDir% 环境变量中设置。<br /><br /> 示例︰ TARGETDIR ="C:\Programs\BizTalk Applications\My 应用程序"|  
  
5.  如果有多台计算机将运行该应用程序，请在每台计算机上重复上述步骤。  
  
     在将运行它的所有计算机上安装应用程序后，你可以从应用程序[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]通过右键单击应用程序的文件夹并单击管理控制台**启动**。 有关完整说明，请参阅[如何启动和停止 BizTalk 应用程序](../core/how-to-start-and-stop-a-biztalk-application.md)。  
  
## <a name="see-also"></a>另请参阅  
 [部署 BizTalk 应用程序](../core/deploying-biztalk-applications.md)   
 [如何卸载 BizTalk 应用程序](../core/how-to-uninstall-a-biztalk-application.md)