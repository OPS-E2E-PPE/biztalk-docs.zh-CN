---
title: 如何将 BizTalk 程序集添加到应用程序 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [applications], adding assemblies
- assemblies, applications
- managing [assemblies], adding to applications
- applications, assemblies
- managing [assemblies], applications
ms.assetid: 1525a0f6-cb0f-43bf-a851-40c06ab2135e
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3abf79f4c205e336704a40dc885a3645aa354591
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387403"
---
# <a name="how-to-add-a-biztalk-assembly-to-an-application"></a>如何将 BizTalk 程序集添加到应用程序
本主题介绍如何使用 BizTalk Server 管理控制台或命令行向应用程序添加 BizTalk 程序集。  
  
 当将 BizTalk 程序集添加到应用程序，请记住以下重要事项：  
  
-   如果你想要添加程序集并使用该应用程序中已存在的相同本地唯一标识符 (LUID) 覆盖程序集，指定覆盖选项。 如果未指定，且具有相同 LUID 的程序集已添加的程序集存在该操作将失败的应用程序中。 LUID 包括程序集文件的名称、 版本、 区域性和公钥标记。 可以通过使用应用程序中查看项目的 Luid [ListApp 命令](../core/listapp-command.md)。  
  
-   如果要添加的程序集不包含在应用程序中的另一个项目上具有依赖项，则添加操作将失败。  
  
-   当添加 BizTalk 程序集时，可以指定一个或多个程序集安装到全局程序集缓存 (GAC 中) 的以下选项：  
  
    -   **将添加到全局程序集缓存添加资源 (gacutil)。** 在选择此选项，程序集安装在本地计算机上的 GAC 中，该程序集添加到应用程序，由于使用本主题中的过程时。  
  
    -   **将添加到 MSI 文件导入 (gacutil) 上的全局程序集缓存。** 当选中此选项时，如果应用程序导出到.msi 文件，并且该.msi 文件导入到 BizTalk 组，导入过程的一部分在本地计算机上的 GAC 中安装该程序集。  
  
    -   **添加到全局程序集缓存 (gacutil) 安装 MSI 文件。** 当选择此选项时，如果应用程序导出到.msi 文件，并根据该.msi 文件的计算机上安装应用程序时，作为安装过程的一部分在本地计算机上的 GAC 中安装该程序集。  
  
## <a name="prerequisites"></a>先决条件  
 若要执行本主题中的过程，必须是 BizTalk Server Administrators 组的成员的帐户登录。 有关详细的权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。  
  
## <a name="to-add-a-biztalk-assembly-to-an-application"></a>若要向应用程序添加 BizTalk 程序集  
  
#### <a name="using-the-biztalk-server-administration-console"></a>使用 BizTalk Server 管理控制台  
  
1. 单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2. 在控制台树中，展开 BizTalk Server 管理和包含你想要添加 BizTalk 程序集的应用程序的 BizTalk 组。  
  
3. 展开应用程序和你想要添加 BizTalk 程序集的应用程序。  
  
4. 右键单击**资源**，依次指向**添加**，然后单击**BizTalk 程序集**。  
  
5. 单击**外**，选择 BizTalk 程序集文件，并单击**打开**。  
  
6. 在中**目标**，键入从.msi 文件，包括文件名称安装该应用程序时要复制的程序集文件所在的位置的完整路径。 如果未提供，该程序集文件不复制到本地文件系统在安装过程。  
  
7. 在中**选项**，为 BizTalk 程序集安装到 GAC 中，指定选项，然后单击**确定**。  
  
#### <a name="using-the-command-line"></a>使用命令行  
  
1. 打开命令提示符，如下所示：单击**启动**，单击**运行**，类型`cmd`，然后单击**确定**。  
  
2. 键入以下命令，替换适当的值下, 表中所述：  
  
    **BTSTask AddResource** [**/ApplicationName:**<em>值</em>] **/Type:System.BizTalk:BizTalkAssembly** [**/Overwrite**] **/Source:**<em>值</em>[**/Destination:**<em>值</em>] [**/Options:GacOnAdd** &#124; **GacOnInstall**&#124;**GacOnImport**] [**/Server:**<em>值</em>] [**/数据库：**<em>值</em>]  
  
    例如：  
  
    **BTSTask AddResource /ApplicationName:MyApplication /Type:System.BizTalk:BizTalkAssembly / 覆盖 /Source:"C:\BizTalk Assemblies\MyOrchestration.dll"/Destination:"C:\New BizTalk Assemblies\ MyOrchestration.dll"/Server:我 /Database:BizTalkMgmtDb**  
  
   |参数|ReplTest1|  
   |---------------|-----------|  
   |**/ApplicationName**|要向其中添加 BizTalk 程序集的 BizTalk 应用程序的名称。 如果未指定应用程序名称，则使用默认 BizTalk 应用程序。 如果名称包含空格，则必须将其括在双引号 （"）。|  
   |**/Type**|**System.BizTalk:BizTalkAssembly**|  
   |**/Overwrite**|若要更新的现有程序集的选项。 如果未指定，且程序集已经存在具有相同 LUID 的程序集添加，则 AddResource 操作将失败的应用程序中。 可以通过使用应用程序中查看项目的 Luid [ListApp 命令](../core/listapp-command.md)。 如果另一个应用程序依赖于被覆盖的程序集，则 AddResource 操作将失败，即使指定了此参数。|  
   |**/Source**|包括文件名称的程序集文件的完整路径。 如果路径包含空格，则必须将其括在双引号 （"）。|  
   |**/ 目标**|程序集文件从.msi 文件安装应用程序时要复制的位置的完整路径。 如果未提供，该程序集文件不复制到本地文件系统在安装过程。 如果路径包含空格，则必须将其括在双引号 （"）。|  
   |**/ 选项**|-   **GacOnAdd**:指定将程序集安装到全局程序集缓存 (GAC) 在本地计算机上在 AddResource 操作过程。<br />-   **GacOnInstall**:指定从.msi 文件安装应用程序时，将程序集安装到 GAC。<br />-   **GacOnImport**:指定要导入应用程序.msi 文件时，将程序集安装到 GAC。<br /><br /> 必须用逗号分隔多个选项。|  
   |**/Server**|承载 BizTalk 管理数据库，在窗体 ServerName\InstanceName，端口中的 SQL Server 实例的名称。<br /><br /> 实例名称仅是所需的实例名称不同于服务器名称时。 端口是仅在 SQL Server 使用的端口号而不是默认 (1433) 时所需。<br /><br /> 示例：<br /><br /> Server=MyServer<br /><br /> Server=MyServer\MySQLServer,1533<br /><br /> 如果未提供，则使用本地计算机上运行的 SQL Server 实例的名称。|  
   |**/Database**|BizTalk 管理数据库的名称。 如果未指定，使用 SQL Server 的本地实例中运行的 BizTalk 管理数据库。|  
  
## <a name="see-also"></a>请参阅  
 [管理 BizTalk 程序集](../core/managing-biztalk-assemblies.md)   
 [AddResource 命令：BizTalk 程序集](../core/addresource-command-biztalk-assembly.md)