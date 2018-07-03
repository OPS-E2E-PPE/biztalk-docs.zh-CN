---
title: 将绑定文件添加到应用程序 |Microsoft Docs
description: 添加绑定文件使用 BizTalk Server 管理或使用 BizTalk Server 中的命令提示符
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1543ee5f-9ae4-4683-b6fe-ee84028c381d
caps.latest.revision: 22
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 772bd4d90087f681ebd6a7934fb56caddb986e91
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37010614"
---
# <a name="add-a-binding-file-to-an-application"></a>将绑定文件添加到应用程序

## <a name="overview"></a>概述
使用 BizTalk Server 管理控制台或命令行向 BizTalk 应用程序添加绑定文件。 你可能想要执行此操作以使应用程序集部署更容易，如中所述[绑定文件和应用程序部署](../core/binding-files-and-application-deployment.md)。  
  
 可以从 BizTalk 应用程序的程序集、 应用程序或组，导出到.xml 文件的绑定，如中所述[导出绑定](../core/exporting-bindings6.md)，以及如何将其中一个过程本主题中，将绑定文件添加到应用程序。  
  
 在您这样做了之后，该绑定文件将添加到 BizTalk 管理数据库并显示在 BizTalk Server 管理控制台的应用程序的“资源”文件夹中。 与导入绑定文件不同，添加绑定文件并不会立即应用其绑定。 而是在将应用程序导入到其他 BizTalk 组时应用绑定。  
  
> [!IMPORTANT]
>  为安全起见，在导出绑定时，BizTalk Server 会从该文件中删除绑定的密码。 在导入绑定后，必须为发送端口和接收位置重新配置密码，它们才能正常运行。 您需要在 BizTalk Server 管理控制台的“传输属性”对话框中为发送端口或接收位置配置密码。 请参阅[创建一个发送端口](../core/how-to-create-a-send-port2.md)或[创建接收位置](../core/how-to-create-a-receive-location.md)。  
  
> [!NOTE]
>  当使用绑定文件时，应验证项目已绑定到正确的主机和信任级别正确。  
  
 在您将某一绑定文件添加到应用程序时，可以通过表示环境的字符串（例如“Test”或“Production”）为目标部署环境指定一个值。 您可以将任何字符串用于该值。 然后，在您导入应用程序时，可以通过提供已为其目标环境指定的值，选择要应用的绑定文件。 这样做了之后，将会从该绑定文件应用这些绑定。 应用程序中与该文件中的绑定同名的所有现有绑定都将被自动覆盖。  
  
 导入应用程序时，绑定按如下顺序应用。 由于绑定在导入过程中应用，所以已应用的绑定将被同名的新绑定所覆盖。 换言之，将应用的具有特定名称的最后一个绑定生效。  
  
1. 由 BizTalk Server 生成的、未通过绑定文件显式添加到应用程序但用户已经显式选择导出到应用程序 .msi 文件的应用程序绑定。  
  
2. 已经显式添加但尚未指定目标部署环境的绑定文件。 本组中的绑定可以按任何顺序应用。  
  
3. 已经显式添加并且具有与为导入应用程序而选的部署环境相匹配的关联目标部署环境的绑定。 本组中的绑定可以按任何顺序应用。  
  
   有关导入应用程序和应用绑定的详细信息，请参阅[导入 BizTalk 应用程序](../core/how-to-import-a-biztalk-application.md)。  
  
## <a name="prerequisites"></a>必要條件  
使用 BizTalk Server Administrators 组的成员帐户登录。 [用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)提供了更多详细信息。
  
## <a name="add-a-binding-file-using-biztalk-administration"></a>添加绑定文件使用 BizTalk 管理  
  
1.  打开**BizTalk Server 管理**（在开始菜单中）。
  
2.  展开 BizTalk Server 管理、 相应的 BizTalk 组、 应用程序，和右键单击你想要将绑定文件添加应用的程序。  
  
3.  指向**外**，然后单击**资源**。  
  
4.  单击**外**，选择要添加，并单击的文件**打开**。  
  
5.  若要覆盖具有相同的文件名的此应用程序中的现有绑定文件，请选择**覆盖所有**复选框。 如果存在同名的其他文件，并且您没有选中此复选框，则添加操作将失败。  
  
6.  在中**文件类型**下拉列表中，选择**system.biztalk: biztalkbinding**。  
  
7.  在中**目标环境**，键入一个字符串来表示要应用，例如测试，并单击此文件中的绑定的目标部署环境**确定**。  
  
    > [!IMPORTANT]
    >  如果您将此字段保留为空，则在应用程序导入时将始终应用此文件中的绑定。  
  
     绑定文件将被添加，并且该文件将显示在应用程序的“资源”文件夹中。  
  
## <a name="add-a-binding-file-using-the-command-line"></a>添加绑定文件使用命令行  
  
1. 打开命令提示符 (**启动**菜单 > 输入`cmd`> 选择**命令提示符下**)。  
  
2. 键入以下命令，替换适当的值下, 表中所述：  
  
    **BTSTask AddResource** [**/ApplicationName:"**<em>值</em>**"**] **/Type:System.BizTalk:BizTalkBinding** [**/Overwrite**] **/source:**<em>值</em>**/Property:TargetEnvironment ="**<em>值</em>**"** [**/Server:**<em>值</em>] [**/database:**<em>值</em>]  
  
    例如：  
  
    **BTSTask AddResource /ApplicationName:"我的应用程序"/Type:System.BizTalk:BizTalkBinding /Source:"C:\Binding Files\MyBinding.xml"/Property:TargetEnvironment ="生产"/Server:MyDatabaseServer /Database:BizTalkMgmtDb**  
  
   |参数|ReplTest1|  
   |---------------|-----------|  
   |**/ 应用程序名称**|绑定文件要添加到的 BizTalk 应用程序的名称。 如果未指定应用程序名称，则将使用默认 BizTalk 应用程序。 如果名称包含空格，则必须将其括在双引号 （"）。|  
   |**/ 类型**|**System.biztalk: biztalkbinding** （此值不区分大小写。）|  
   |**/ 覆盖**|更新现有绑定文件的选项。 如果未指定，且绑定文件已存在与要添加的文件具有相同文件名的应用程序中，则 AddResource 操作将失败。|  
   |**/ 源**|绑定文件的完整路径，包含文件名。 如果路径包含空格，则必须将其括在双引号 （"）。|  
   |**/Property:TargetEnvironment =**|指定目标部署环境的字符串。 您可以使用任何字符串，如 Production。 示例： **/Property:TargetEnvironment ="生产"**<br /><br /> 如果未指定的值\<默认\>自动应用。 该值区分大小写。 如果该值包含空格，则必须将其括在双引号 (") 中。 环境值的最大长度为 128 个字符。|  
   |**/ 服务器**|BizTalk 管理数据库的宿主 SQL Server 实例的名称，格式为“服务器名称\实例名称,端口”。<br /><br /> 只在实例名称与服务器名称不相同时才需要指定实例名称。 只在 SQL Server 不使用默认端口号 (1433) 时才需要指定端口。<br /><br /> 示例：<br /><br /> Server=MyServer<br /><br /> Server=MyServer\MySQLServer,1533<br /><br /> 如果未提供，则使用本地计算机上运行的 SQL Server 实例的名称。|  
   |**/ 数据库**|BizTalk 管理数据库的名称。 如果未指定，则使用在本地 SQL Server 实例中运行的 BizTalk 管理数据库。|  
  
## <a name="see-also"></a>请参阅  
 [管理.NET 程序集、 证书和其他资源](../core/managing-net-assemblies-certificates-and-other-resources.md)   
 [AddResource 命令： BizTalk 绑定](../core/addresource-command-biztalk-binding.md)   
 [创建和修改 BizTalk 应用程序](../core/creating-and-modifying-biztalk-applications.md)