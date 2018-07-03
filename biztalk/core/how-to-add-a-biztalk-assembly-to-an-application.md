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
ms.openlocfilehash: 1e6921612c84d3f37604e1330195c1c652d5b3fe
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37008534"
---
# <a name="how-to-add-a-biztalk-assembly-to-an-application"></a>如何向应用程序中添加 BizTalk 程序集
本主题介绍如何使用 BizTalk Server 管理控制台或命令行向应用程序添加 BizTalk 程序集。  
  
 向应用程序中添加 BizTalk 程序集时，请切记以下几点：  
  
-   如果您要使用已在应用程序中存在的相同本地唯一标识符 (LUID) 添加某一程序集和覆盖某一程序集，则指定“Overwrite”选项。 如果未指定，且应用程序中已存在与要添加的程序集具有相同 LUID 的程序集，则该操作将失败。 LUID 包括程序集文件名、版本、区域性和公钥标记。 可以通过使用应用程序中查看项目的 Luid [ListApp 命令](../core/listapp-command.md)。  
  
-   如果要添加的程序集依赖于并未包含在该应用程序中的其他项目，则添加操作将失败。  
  
-   在添加某一 BizTalk 程序集时，可以指定以下一个或多个选项，以便将该程序集安装到全局程序集缓存 (GAC) 中：  
  
    -   **将添加到全局程序集缓存添加资源 (gacutil)。** 如果您选择了此选项，则在按照本主题中介绍的过程将程序集添加到某一应用程序时，该程序集就会安装到本地计算机上的 GAC 中。  
  
    -   **将添加到 MSI 文件导入 (gacutil) 上的全局程序集缓存。** 如果您选择了此选项，则在应用程序导出到某一 .msi 文件，然后该 .msi 文件导入到 BizTalk 组时，程序集将作为导入过程的一部分安装到本地计算机上的 GAC 中。  
  
    -   **添加到全局程序集缓存 (gacutil) 安装 MSI 文件。** 如果您选择了此选项，则在应用程序导出到某一 .msi 文件，然后应用程序根据该 .msi 文件安装到某一计算机时，程序集将作为安装过程的一部分安装到本地计算机上的 GAC 中。  
  
## <a name="prerequisites"></a>必要條件  
 若要执行本主题中的过程，必须是 BizTalk Server Administrators 组的成员的帐户登录。 有关详细的权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。  
  
## <a name="to-add-a-biztalk-assembly-to-an-application"></a>向应用程序中添加 BizTalk 程序集  
  
#### <a name="using-the-biztalk-server-administration-console"></a>使用 BizTalk Server 管理控制台  
  
1. 单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2. 在控制台树中，展开 BizTalk Server 管理和包含你想要添加 BizTalk 程序集的应用程序的 BizTalk 组。  
  
3. 展开包含要添加 BizTalk 程序集的应用程序。  
  
4. 右键单击**资源**，依次指向**添加**，然后单击**BizTalk 程序集**。  
  
5. 单击**外**，选择 BizTalk 程序集文件，并单击**打开**。  
  
6. 在中**目标**，键入从.msi 文件，包括文件名称安装该应用程序时要复制的程序集文件所在的位置的完整路径。 如果未提供，则安装期间该程序集文件将不会复制到本地文件系统。  
  
7. 在中**选项**，为 BizTalk 程序集安装到 GAC 中，指定选项，然后单击**确定**。  
  
#### <a name="using-the-command-line"></a>使用命令行  
  
1. 按如下所示打开命令提示符： 单击**启动**，单击**运行**，类型`cmd`，然后单击**确定**。  
  
2. 键入以下命令，替换适当的值下, 表中所述：  
  
    **BTSTask AddResource** [**/ApplicationName:**<em>值</em>] **/Type:System.BizTalk:BizTalkAssembly** [**/Overwrite**] **/Source:**<em>值</em>[**/Destination:**<em>值</em>] [**/Options:GacOnAdd** &#124; **GacOnInstall**&#124;**GacOnImport**] [**/Server:**<em>值</em>] [**/数据库：**<em>值</em>]  
  
    例如：  
  
    **BTSTask AddResource /ApplicationName:MyApplication /Type:System.BizTalk:BizTalkAssembly / 覆盖 /Source:"C:\BizTalk Assemblies\MyOrchestration.dll"/Destination:"C:\New BizTalk Assemblies\ MyOrchestration.dll"/Server:我 /Database:BizTalkMgmtDb**  
  
   |参数|ReplTest1|  
   |---------------|-----------|  
   |**/ 应用程序名称**|向其添加 BizTalk 程序集的 BizTalk 应用程序的名称。 如果未指定应用程序名称，则将使用默认 BizTalk 应用程序。 如果名称包含空格，则必须将其括在双引号 （"）。|  
   |**/ 类型**|**System.biztalk: biztalkassembly**|  
   |**/ 覆盖**|更新现有程序集的选项。 如果未指定，且应用程序中已存在与要添加的程序集具有相同 LUID 的程序集，则 AddResource 操作将失败。 可以通过使用应用程序中查看项目的 Luid [ListApp 命令](../core/listapp-command.md)。 如果其他应用程序依赖于要覆盖的程序集，则即使指定了此参数，AddResource 操作也会失败。|  
   |**/ 源**|程序集文件的完整路径，包含文件名。 如果路径包含空格，则必须将其括在双引号 （"）。|  
   |**/ 目标**|从 .msi 文件安装应用程序时，程序集文件要复制到的位置的完整路径。 如果未提供，则安装期间该程序集文件将不会复制到本地文件系统。 如果路径包含空格，则必须将其括在双引号 （"）。|  
   |**/ 选项**|-   **GacOnAdd**： 指定程序集安装到全局程序集缓存 (GAC) 在本地计算机上在 AddResource 操作过程。<br />-   **GacOnInstall**： 指定当从.msi 文件安装应用程序时，将程序集安装到 GAC。<br />-   **GacOnImport**： 指定导入应用程序.msi 文件时，将程序集安装到 GAC。<br /><br /> 多个选项之间必须用逗号分开。|  
   |**/ 服务器**|BizTalk 管理数据库的宿主 SQL Server 实例的名称，格式为“服务器名称\实例名称,端口”。<br /><br /> 只在实例名称与服务器名称不相同时才需要指定实例名称。 只在 SQL Server 不使用默认端口号 (1433) 时才需要指定端口。<br /><br /> 示例：<br /><br /> Server=MyServer<br /><br /> Server=MyServer\MySQLServer,1533<br /><br /> 如果未提供，则使用本地计算机上运行的 SQL Server 实例的名称。|  
   |**/ 数据库**|BizTalk 管理数据库的名称。 如果未指定，则使用在本地 SQL Server 实例中运行的 BizTalk 管理数据库。|  
  
## <a name="see-also"></a>请参阅  
 [管理 BizTalk 程序集](../core/managing-biztalk-assemblies.md)   
 [AddResource 命令：BizTalk 程序集](../core/addresource-command-biztalk-assembly.md)