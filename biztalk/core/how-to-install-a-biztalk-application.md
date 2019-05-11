---
title: 如何安装 BizTalk 应用程序 |Microsoft Docs
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
caps.latest.revision: 56
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1945a084d834bd7f603557854a7977d20da213a7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65384931"
---
# <a name="how-to-install-a-biztalk-application"></a>如何安装 BizTalk 应用程序
本主题介绍如何通过双击 Windows 界面中的应用程序的 Windows Installer (.msi) 文件或通过从命令行运行 msiexec 来在本地计算机上安装应用程序。 也可以启动安装向导导入向导的最后一步中所述[导入 BizTalk 应用程序的方式](../core/how-to-import-a-biztalk-application.md)。  

> [!CAUTION]
>  如果已在此计算机上安装此应用程序，将为您提供修复应用程序的选项。 仅当已为此应用程序安装了单个.msi 时，才支持修复。 如果已在此应用程序的计算机上安装多个.msi，不应选择此选项。 这是因为选择修复将撤消所做的.msi 文件安装此.msi 文件中，这可能会导致你的应用程序无法正常工作之后的任何更改。  

 可以将应用程序分成操作之前，必须将其安装在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将运行它的计算机。 安装应用程序在本地文件系统上放置其资源。 具体取决于应用程序，其内容，以及其配置，安装可能还执行以下操作：  

- 将程序集添加到全局程序集缓存 (GAC)  

- 安装证书和虚拟目录  

- 将组件添加到 Windows 注册表。  

- 如果.msi 文件中存在，请运行预处理或后处理脚本。  

  有关背景信息，请参阅[有什么变故项目期间安装和卸载](../core/what-happens-to-artifacts-during-installation-and-uninstallation.md)。  

## <a name="prerequisites"></a>先决条件  
 若要执行本主题中的过程，必须在本地文件系统上具有写权限的帐户登录。 具体取决于应用程序中包含的项，您可能还需要编写在 Windows 注册表、 GAC、 证书存储区和 Internet Information Services 上的权限。 在本地计算机上的管理员帐户拥有这些权限。 有关详细的权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。  

## <a name="considerations-for-installing-an-application"></a>安装应用程序的注意事项  
 当安装的应用程序，可能适用以下注意事项：  

- **此外必须安装此应用程序所依赖的任何应用程序。** 当安装某个项目，如 BizTalk 程序集，其中包含在另一个应用程序中，具有一个依赖项的应用程序时还必须安装包含该项目的应用程序。 在可以运行该应用程序之前必须执行此操作。 例如，如果应用程序 A 依赖于应用程序 B 中的程序集，您还必须安装应用程序 b。然后，你可以安装应用程序 a。有关背景信息，请参阅[依赖项和应用程序部署](../core/dependencies-and-application-deployment.md)。  

- **您应停止要更新的应用程序。** 如果正在执行安装以更新应用程序中的项目，您不需要停止应用程序，除非更新中包含一个或多个程序集具有与现有程序集相同的版本。 在这种情况下，必须停止再安装此更新应用程序。 但是，我们建议您停止应用程序在所有情况下，除非您知道，更新不会干扰应用程序运行。 有关详细信息，请参阅[更新 BizTalk 应用程序](../core/updating-biztalk-applications.md)。  

- **安装在同一应用程序的多个.msi 文件时，没有中添加或删除程序所做的一项。** 你可能会执行此选项以更新现有的应用程序，例如。 你可以然后使用添加或删除程序 （在控制面板中） 完全卸载该应用程序包括任何更新的项目。 请注意，不支持通过双击.msi 文件或使用 msiexec 来卸载应用程序。 有关详细信息，请参阅[如何卸载 BizTalk 应用程序](../core/how-to-uninstall-a-biztalk-application.md)。  

- **证书必须存在才能运行应用程序承载发送端口的所有计算机上。** 其他人证书存储区包含发送端口使用的证书。  

- **可以为不同的.msi 文件安装以便将应用程序项目。** 不需要将运行该应用程序的每台计算机上安装所有应用程序项目。 相反，您可以导出到不同的.msi 文件安装在不同计算机上的应用程序项目的子集。 有关说明，请参阅[如何导出 BizTalk 应用程序](../core/how-to-export-a-biztalk-application.md)。  

- **如果应用程序.msi 文件中包括虚拟目录，则必须在本地计算机上运行 Internet 信息服务 (IIS)。** 如果不存在，则安装将失败。  

- **如果应用程序包含与一个本地计算机上已存在同名的虚拟目录，从应用程序的资源会添加到它。** 否则，创建虚拟目录。 具有相同的名称，如添加的文件将覆盖任何现有文件。 此外，不更改现有的虚拟目录的安全设置，且应验证其足够安全。  

- **安装应用程序之前创建的虚拟目录的应用程序池。** 如果你的应用程序中包括虚拟目录，并且应用程序池在 IIS 中尚不存在，应手动创建应用程序池，然后安装。 这样一来，虚拟目录将绑定到应用程序池在安装过程。 如果不创建应用程序，虚拟目录将绑定到上安装的默认应用程序池。  

- **请确保 BTSHttpReceive.dll 注册为处理程序映射使用 Internet 信息服务 (IIS) 7.0。** 如果你的应用程序按顺序包含虚拟目录，为 HTTP 接收位置工作时，必须执行此操作。  

- **安装包括 64 位项目的 32 位计算机上的应用程序时，可能会遇到问题。** 有关详细信息，请参阅[如何向应用程序添加 64 位项目](../core/how-to-add-a-64-bit-artifact-to-an-application.md)。  

- **如果目标目录长度超过 260 个字符，可能会遇到问题。** 如果在安装 MSI 包过程中指定的目标目录中的字符数超过 260 个字符的安装将失败。 若要解决此问题，请确保为目标目录指定的字符数不超过 260 个字符。  

- **不应重新定位安装文件夹。** 后安装应用程序，您不应重新定位安装文件夹或其包含的文件。 如果这样做，然后以后尝试删除 （卸载） 应用程序中，删除操作将失败。 具体而言，应用程序安装文件夹包含生成的文件[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]的所需执行删除操作。 不应重命名、 移动或删除这些文件。 文件包括：  

  -   ApplicationDefinition.adf  

  -   Microsoft.BizTalk.CustomInstaller.dll  

  -   Microsoft.BizTalk.CustomInstaller.InstallState  

> [!NOTE]
>  如果在完成之前取消安装操作[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将回滚安装过程中，该操作已取消之前由预处理或后处理脚本执行的操作除外。  
> 
> [!IMPORTANT]
>  然后再安装任何应用程序，请确保已从受信任的源接收的.msi 文件。 恶意用户可以在可以有不良影响系统或网络上的.msi 文件中包括代码。  有关详细信息，请参阅[安全性和 Windows 安装程序](../core/security-and-windows-installer.md)。  
> 
>  如果应用程序包括一个网站还是使用 Web 服务的业务流程，请注意上的虚拟目录的安全设置是指那些是有效的.msi 文件生成时应用程序在导出期间，除在现有的情况下虚拟目录，将使用的现有设置。 在安装后该应用程序，应验证设置满足安全要求。  
> 
>  导出应用程序时，将从文件和文件夹中删除 Alldiscretionary 访问控制列表 (Dacl)。 主机实例上安装应用程序之后, 必须重新配置文件和文件夹，包括虚拟目录上的所有安全设置。  

-   **可能需要进行更改的本地路径： 指定的虚拟目录的引用的 HTTP 接收位置后在目标计算机上创建。**  

     在目标计算机上创建虚拟目录时它将指向以下物理目录之一：  

     \<*installation drive*\>\Program Files\Microsoft BizTalk Server\HttpReceive  

     \- **或**–  

     \<*installation drive*\>\Program Files (x86)\Microsoft BizTalk Server\HttpReceive  

     如果 BizTalk HTTP 接收 ISAPI 扩展 BTSHTTPReceive.dll 不位于指定的目录，或者如果目标计算机正在运行 64 位操作系统，则必须更改的本地路径： 指定的虚拟目录以指向物理目录包含该 BizTalk HTTP 接收 ISAPI 扩展文件。 例如，如果目标计算机正在运行的 64 位版本的 Windows Vista 中，然后本地路径： 目标虚拟目录应更改为\<安装驱动器\>\Program 文件 (x86) \Microsoft BizTalk Server\HttpReceive64。  

## <a name="to-install-a-biztalk-application"></a>若要安装 BizTalk 应用程序  

#### <a name="using-the-windows-interface"></a>使用 Windows 界面  

1. 将复制到本地计算机应用程序的.msi 文件。  

2. 如果您要重新安装或升级现有的 BizTalk 应用程序，并且新安装包括具有相同版本作为一个已存在于应用程序，或与你要更新的项目进行交互的程序集，请确保应用程序已停止通过右键单击应用程序文件夹，然后单击**停止**。  

3. 在 Windows 资源管理器，双击.msi 文件以启动安装向导。  

4. 上**选择安装文件夹**页上，在**文件夹**，键入 BizTalk 应用程序的完整安装路径。 例如：通过 BizTalk\MyApplication C:\Program Files\Generated。  

5. 单击**下一步**四次，然后在**安装完整**页上，单击**关闭**。  

6. 如果多台计算机将运行应用程序，请重复前面的步骤，每台计算机上。  

    将运行它的所有计算机上安装应用程序和应用程序是否已导入 BizTalk 组，你可以启动该应用程序从[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中右键单击应用程序的文件夹，单击**启动**。 有关完整说明，请参阅[如何启动和停止 BizTalk 应用程序](../core/how-to-start-and-stop-a-biztalk-application.md)。  

#### <a name="using-the-command-line"></a>使用命令行  

1. 将复制到本地计算机应用程序的.msi 文件。  

2. 单击**启动**，单击**运行**，类型`cmd`，然后按 ENTER。  

3. 导航到存储.msi 文件的位置。  

4. 键入以下命令以安装应用程序，提供适当的参数和值下, 表中所示：  

   > [!IMPORTANT]
   >  支持下表中显示的 msiexec 的参数。  

    **msiexec** [**/i**] *Package* [**/qn**] **TARGETDIR="**<em>value</em>**"**]  

    示例： **msiexec /i MyApplication.msi**  


   |           参数           |                                                                                                 ReplTest1                                                                                                 |
   |-------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |            **/i**             |                                                                                       安装应用程序。                                                                                       |
   |           *“包”*           |                                                                              Windows Installer (.msi) 文件的名称。                                                                               |
   |            **/qn**            |                                                                    执行安装而不显示用户界面。                                                                     |
   | **TARGETDIR="** *value* **"** | 指定应用程序安装文件夹。 此值将在 %btad_installdir%环境变量。<br /><br /> 例如：TARGETDIR="C:\Programs\BizTalk Applications\My Application" |


5. 如果多台计算机将运行应用程序，请重复前面的步骤，每台计算机上。  

    一旦将运行它的所有计算机上安装应用程序，即可从应用程序[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中右键单击应用程序的文件夹，单击**启动**。 有关完整说明，请参阅[如何启动和停止 BizTalk 应用程序](../core/how-to-start-and-stop-a-biztalk-application.md)。  

## <a name="see-also"></a>请参阅  
 [部署 BizTalk 应用程序](../core/deploying-biztalk-applications.md)   
 [如何卸载 BizTalk 应用程序](../core/how-to-uninstall-a-biztalk-application.md)