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
ms.openlocfilehash: 302bb98f93f4b0e165d04db1210875bd7737ed28
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65344090"
---
# <a name="add-a-binding-file-to-an-application"></a>将绑定文件添加到应用程序

## <a name="overview"></a>概述
使用 BizTalk Server 管理控制台或命令行向 BizTalk 应用程序添加绑定文件。 你可能想要执行此操作以使应用程序集部署更容易，如中所述[绑定文件和应用程序部署](../core/binding-files-and-application-deployment.md)。  
  
 可以从 BizTalk 应用程序的程序集、 应用程序或组，导出到.xml 文件的绑定，如中所述[导出绑定](../core/exporting-bindings6.md)，以及如何将其中一个过程本主题中，将绑定文件添加到应用程序。  
  
 当执行此操作时，绑定文件添加到 BizTalk 管理数据库，并显示在 BizTalk Server 管理控制台中，应用程序的资源文件夹中。 与导入绑定文件，不同上添加绑定文件不会立即应用其绑定。 相反，应用程序导入到其他 BizTalk 组时应用绑定。  
  
> [!IMPORTANT]
>  出于安全原因，导出绑定时 BizTalk Server 将从文件删除绑定密码。 导入绑定之后, 必须重新配置为发送端口的密码，并接收位置，它们才能正常。 发送端口在 BizTalk Server 管理控制台的传输属性对话框中配置密码，或接收位置。 请参阅[创建一个发送端口](../core/how-to-create-a-send-port2.md)或[创建接收位置](../core/how-to-create-a-receive-location.md)。  
  
> [!NOTE]
>  当使用绑定文件时，应验证项目已绑定到正确的主机和信任级别正确。  
  
 当向应用程序添加绑定文件时，您可以使用一个字符串，表示环境中的，如测试或生产指定目标部署环境的值。 为此值，可以使用任何字符串。 然后，导入应用程序时，你可以选择要应用通过提供的值指定为其目标环境的绑定文件。 当执行此操作时，从绑定文件应用绑定。 自动覆盖任何现有应用程序中绑定文件中具有相同的名称绑定的。  
  
 导入应用程序时，绑定按以下顺序应用。 当导入过程中应用绑定时，已应用的绑定将覆盖具有相同名称的新绑定。 换而言之，具有特定名称的最后一个绑定，应用将生效。  
  
1. 应用程序绑定由 BizTalk Server 生成的未显式添加到应用程序通过绑定文件，但已经显式选择导出到应用程序.msi 文件的用户。  
  
2. 已显式添加，并且没有指定目标部署环境的绑定文件。 在此集中的绑定可以按任何特定顺序应用。  
  
3. 绑定已显式添加的且具有相关联的目标部署环境为应用程序导入选择的部署环境相匹配。 在此集中的绑定可以按任何特定顺序应用。  
  
   有关导入应用程序和应用绑定的详细信息，请参阅[导入 BizTalk 应用程序](../core/how-to-import-a-biztalk-application.md)。  
  
## <a name="prerequisites"></a>先决条件  
使用 BizTalk Server Administrators 组的成员帐户登录。 [用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)提供了更多详细信息。
  
## <a name="add-a-binding-file-using-biztalk-administration"></a>添加绑定文件使用 BizTalk 管理  
  
1.  打开**BizTalk Server 管理**（在开始菜单中）。
  
2.  展开 BizTalk Server 管理、 相应的 BizTalk 组、 应用程序，和右键单击你想要将绑定文件添加应用的程序。  
  
3.  指向**外**，然后单击**资源**。  
  
4.  单击**外**，选择要添加，并单击的文件**打开**。  
  
5.  若要覆盖具有相同的文件名的此应用程序中的现有绑定文件，请选择**覆盖所有**复选框。 如果存在具有相同的名称，另一个文件，并且您未选中此复选框，则添加操作将失败。  
  
6.  在中**文件类型**下拉列表中，选择**system.biztalk: biztalkbinding**。  
  
7.  在中**目标环境**，键入一个字符串来表示要应用，例如测试，并单击此文件中的绑定的目标部署环境**确定**。  
  
    > [!IMPORTANT]
    >  如果将此字段留空，在应用程序导入时将始终应用此文件中的绑定。  
  
     添加绑定文件，并显示在应用程序的资源文件夹中。  
  
## <a name="add-a-binding-file-using-the-command-line"></a>添加绑定文件使用命令行  
  
1. 打开命令提示符 (**启动**菜单 > 输入`cmd`> 选择**命令提示符下**)。  
  
2. 键入以下命令，替换适当的值下, 表中所述：  
  
    **BTSTask AddResource** [**/ApplicationName:"**<em>值</em>**"**] **/Type:System.BizTalk:BizTalkBinding** [**/Overwrite**] **/source:**<em>值</em>**/Property:TargetEnvironment ="**<em>值</em>**"** [**/Server:**<em>值</em>] [**/database:**<em>值</em>]  
  
    例如：  
  
    **BTSTask AddResource /ApplicationName:"我的应用程序"/Type:System.BizTalk:BizTalkBinding /Source:"C:\Binding Files\MyBinding.xml"/Property:TargetEnvironment ="生产"/Server:MyDatabaseServer /Database:BizTalkMgmtDb**  
  
   |参数|ReplTest1|  
   |---------------|-----------|  
   |**/ApplicationName**|要将绑定文件添加到 BizTalk 应用程序的名称。 如果未指定应用程序名称，则使用默认 BizTalk 应用程序。 如果名称包含空格，则必须将其括在双引号 （"）。|  
   |**/Type**|**System.biztalk: biztalkbinding** （此值不区分大小写。）|  
   |**/Overwrite**|若要更新现有绑定文件的选项。 如果未指定，且绑定文件已存在与要添加的文件具有相同文件名的应用程序中，则 AddResource 操作将失败。|  
   |**/Source**|绑定文件，其中包括文件名的完整路径。 如果路径包含空格，则必须将其括在双引号 （"）。|  
   |**/Property:TargetEnvironment=**|一个字符串，指定目标部署环境。 可以使用任意字符串，例如生产。 示例： **/Property:TargetEnvironment ="生产"**<br /><br /> 如果未指定的值\<默认\>自动应用。 值是区分大小写。 如果值包含空格，则必须将其括在双引号 （"）。 环境值的最大长度为 128 个字符。|  
   |**/Server**|承载 BizTalk 管理数据库，在窗体 ServerName\InstanceName，端口中的 SQL Server 实例的名称。<br /><br /> 实例名称仅是所需的实例名称不同于服务器名称时。 端口是仅在 SQL Server 使用的端口号而不是默认 (1433) 时所需。<br /><br /> 示例：<br /><br /> Server=MyServer<br /><br /> Server=MyServer\MySQLServer,1533<br /><br /> 如果未提供，则使用本地计算机上运行的 SQL Server 实例的名称。|  
   |**/Database**|BizTalk 管理数据库的名称。 如果未指定，使用 SQL Server 的本地实例中运行的 BizTalk 管理数据库。|  
  
## <a name="see-also"></a>请参阅  
 [管理.NET 程序集、 证书和其他资源](../core/managing-net-assemblies-certificates-and-other-resources.md)   
 [AddResource 命令：BizTalk 绑定](../core/addresource-command-biztalk-binding.md)   
 [创建和修改 BizTalk 应用程序](../core/creating-and-modifying-biztalk-applications.md)