---
title: "如何将绑定文件添加到 Application2 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- managing [applications], binding files
- applications, binding files
- binding files, applications
ms.assetid: 1543ee5f-9ae4-4683-b6fe-ee84028c381d
caps.latest.revision: "22"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b4e569352c5813272b483cc69b8c93a7f1b84d40
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-add-a-binding-file-to-an-application"></a>如何向应用程序添加绑定文件
本主题描述如何使用 BizTalk Server 管理控制台或命令行向 BizTalk 应用程序添加绑定文件。 你可能想要执行此操作可使应用程序集的部署中所述更容易，[绑定文件和应用程序部署](../core/binding-files-and-application-deployment.md)。  
  
 中所述，你可以从程序集、 应用程序，或组中，BizTalk 应用程序导出到.xml 文件的绑定[导出绑定](../core/exporting-bindings6.md)，并将其中一个过程本主题中，以便将绑定文件添加到应用程序。  
  
 在您这样做了之后，该绑定文件将添加到 BizTalk 管理数据库并显示在 BizTalk Server 管理控制台的应用程序的“资源”文件夹中。 与导入绑定文件不同，添加绑定文件并不会立即应用其绑定。 而是在将应用程序导入到其他 BizTalk 组时应用绑定。  
  
> [!IMPORTANT]
>  为安全起见，在导出绑定时，BizTalk Server 会从该文件中删除绑定的密码。 在导入绑定后，必须为发送端口和接收位置重新配置密码，它们才能正常运行。 您需要在 BizTalk Server 管理控制台的“传输属性”对话框中为发送端口或接收位置配置密码。 有关说明，请参阅[如何创建发送端口](../core/how-to-create-a-send-port2.md)。 另请参阅[如何创建接收位置](../core/how-to-create-a-receive-location.md)。  
  
> [!NOTE]
>  当你使用的绑定文件中生成[!INCLUDE[btsBizTalkServer2004](../includes/btsbiztalkserver2004-md.md)]，请注意，在绑定文件中不存储的主机的信任级别。 在绑定导入或应用程序导入期间应用绑定时，项目将仅基于主机名称绑定到主机。 您应该验证这些项目已绑定到正确的主机并且信任级别也正确。  
  
 在您将某一绑定文件添加到应用程序时，可以通过表示环境的字符串（例如“Test”或“Production”）为目标部署环境指定一个值。 您可以将任何字符串用于该值。 然后，在您导入应用程序时，可以通过提供已为其目标环境指定的值，选择要应用的绑定文件。 这样做了之后，将会从该绑定文件应用这些绑定。 应用程序中与该文件中的绑定同名的所有现有绑定都将被自动覆盖。  
  
 导入应用程序时，绑定按如下顺序应用。 由于绑定在导入过程中应用，所以已应用的绑定将被同名的新绑定所覆盖。 换言之，将应用的具有特定名称的最后一个绑定生效。  
  
1.  由 BizTalk Server 生成的、未通过绑定文件显式添加到应用程序但用户已经显式选择导出到应用程序 .msi 文件的应用程序绑定。  
  
2.  已经显式添加但尚未指定目标部署环境的绑定文件。 本组中的绑定可以按任何顺序应用。  
  
3.  已经显式添加并且具有与为导入应用程序而选的部署环境相匹配的关联目标部署环境的绑定。 本组中的绑定可以按任何顺序应用。  
  
 有关导入应用程序和应用绑定的详细信息，请参阅[如何导入 BizTalk 应用程序](../core/how-to-import-a-biztalk-application.md)。  
  
## <a name="prerequisites"></a>先决条件  
 若要执行本主题中的过程，必须使用 BizTalk Server Administrators 组的成员帐户登录。 有关更多详细权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。  
  
## <a name="to-add-a-binding-file-to-an-application"></a>向应用程序添加绑定文件  
  
#### <a name="using-the-biztalk-server-administration-console"></a>使用 BizTalk Server 管理控制台  
  
1.  单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2.  在控制台树中，展开“[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] 管理”，然后展开包含要添加绑定文件的应用程序的 BizTalk 组。  
  
3.  展开“应用程序”，右键单击您要向其添加绑定文件的应用程序。  
  
4.  指向**添加**，然后单击**资源**。  
  
5.  单击**添加**，选择要添加，，然后单击的文件**打开**。  
  
6.  若要覆盖现有绑定文件具有相同的文件名称此应用程序中，选择**覆盖所有**复选框。 如果存在同名的其他文件，并且您没有选中此复选框，则添加操作将失败。  
  
7.  在**文件类型**下拉列表中，选择**System.BizTalk:BizTalkBinding**。  
  
8.  在**目标环境**，键入字符串来表示想将此文件中的绑定应用，例如测试，然后单击其中的目标部署环境**确定**。  
  
    > [!IMPORTANT]
    >  如果您将此字段保留为空，则在应用程序导入时将始终应用此文件中的绑定。  
  
     绑定文件将被添加，并且该文件将显示在应用程序的“资源”文件夹中。  
  
#### <a name="using-the-command-line"></a>使用命令行  
  
1.  如下所示打开命令提示符： 单击**启动**，单击**运行**，类型`cmd`，然后单击**确定**。  
  
2.  键入以下命令，替换为适当的值下, 表中所述：  
  
     **BTSTask AddResource** [**/ApplicationName:"***值***"**] **/Type:System.BizTalk:BizTalkBinding** [**/覆盖**] **/source:***值***/Property:TargetEnvironment ="***值* **"** [**/Server:***值*] [**/数据库：***值*]  
  
     例如：  
  
     **BTSTask AddResource /ApplicationName:"我的应用程序"/Type:System.BizTalk:BizTalkBinding /Source:"C:\Binding Files\MyBinding.xml"/Property:TargetEnvironment ="Production"/Server:MyDatabaseServer /Database:BizTalkMgmtDb**  
  
    |参数|值|  
    |---------------|-----------|  
    |**/ 应用程序名称**|绑定文件要添加到的 BizTalk 应用程序的名称。 如果未指定应用程序名称，则将使用默认 BizTalk 应用程序。 如果名称包含空格，必须将它括在双引号 （"）。|  
    |**/ 类型**|**System.BizTalk:BizTalkBinding** （此值不区分大小写。）|  
    |**/ 覆盖**|更新现有绑定文件的选项。 如果没有指定，且有约束力的文件中的应用程序与正在添加的文件具有相同的文件名称已存在，则 AddResource 操作将失败。|  
    |**/ 源**|绑定文件的完整路径，包含文件名。 如果路径包含空格，必须将它括在双引号 （"）。|  
    |**/Property:TargetEnvironment =**|指定目标部署环境的字符串。 您可以使用任何字符串，如 Production。 示例： **/Property:TargetEnvironment ="Production"**<br /><br /> 如果未指定，值为\<默认 > 自动应用。 该值区分大小写。 如果该值包含空格，则必须将其括在双引号 (") 中。 环境值的最大长度为 128 个字符。|  
    |**/ 服务器**|BizTalk 管理数据库的宿主 SQL Server 实例的名称，格式为“服务器名称\实例名称,端口”。<br /><br /> 只在实例名称与服务器名称不相同时才需要指定实例名称。 只在 SQL Server 不使用默认端口号 (1433) 时才需要指定端口。<br /><br /> 示例：<br /><br /> Server=MyServer<br /><br /> Server=MyServer\MySQLServer,1533<br /><br /> 如果未提供，则使用本地计算机上运行的 SQL Server 实例的名称。|  
    |**/ 数据库**|BizTalk 管理数据库的名称。 如果未指定，则使用在本地 SQL Server 实例中运行的 BizTalk 管理数据库。|  
  
## <a name="see-also"></a>另请参阅  
 [管理.NET 程序集、 证书和其他资源](../core/managing-net-assemblies-certificates-and-other-resources.md)   
 [AddResource 命令： BizTalk 绑定](../core/addresource-command-biztalk-binding.md)   
 [创建和修改 BizTalk 应用程序](../core/creating-and-modifying-biztalk-applications.md)