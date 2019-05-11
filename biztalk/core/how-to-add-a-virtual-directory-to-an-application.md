---
title: 如何将虚拟目录添加到应用程序 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- virtual directories
- managing [applications], virtual directories
- applications, virtual directories
- virtual directories, applications
ms.assetid: a5726696-bd65-49d9-8814-a078afe8c067
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8bfd9c47fbd25c57d1c025806e5eb9dae6bda72b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65343305"
---
# <a name="how-to-add-a-virtual-directory-to-an-application"></a>如何将虚拟目录添加到应用程序
本主题介绍如何使用 BTSTask 命令行工具将虚拟目录添加到 BizTalk 应用程序。 此选项不可用在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。 你可能想要添加虚拟目录，如果您具有编写自定义 Web 服务或创建与进行连接的 ASP.NET Web 站点[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]并且想要部署的虚拟目录与应用程序。  
  
 另一种方法添加到应用程序的虚拟目录是虚拟目录指定的 SOAP 或 HTTP 接收位置，如中所述[如何配置 HTTP 接收位置](../core/how-to-configure-an-http-receive-location.md)。 在所有情况下，虚拟目录添加到 BizTalk 管理数据库。 当使用命令行添加虚拟目录时，它还显示在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中的应用程序添加到资源文件夹，以及使用时的应用程序中的项目列表[ListApp 命令](../core/listapp-command.md)。 如果随后将导出应用程序，然后将其导入到其他 BizTalk 组的虚拟目录显示在资源文件夹中。  
  
 当将虚拟目录添加到应用程序，请记住以下几点：  
  
-   您可以覆盖虚拟目录已存在应用程序中通过指定覆盖选项。 仅当现有的虚拟目录具有与你想要添加的一个同名时，则需要使用覆盖选项。 如果未指定，且虚拟目录已存在具有相同名称作为要添加应用程序中，添加操作将失败。  
  
-   当添加包含 https 的 URL 与虚拟目录时，必须指定而不是 https 的 URL 中使用 http。 如果使用 https 时，要添加虚拟目录的操作将失败。 即使使用 http URL 中将其添加，Internet Information Services 元数据库中的 URL 的 https 设置将生效，和虚拟目录将正常工作。  
  
-   如果从 64 位版本的 Web 服务中，添加虚拟目录，并尝试安装包括 32 位计算机上的虚拟目录的应用程序，将不安装的虚拟目录。 必须在 64 位计算机上安装它。  
  
> [!IMPORTANT]
>  导入包含虚拟目录的应用程序时，虚拟目录上的安全设置是有效应用程序导出期间生成.msi 文件时。 如果要部署到生产环境中，应用程序，然后导出该应用程序，则应验证设置满足安全要求。  
>   
>  如果，但是，虚拟目录已存在目标环境中，现有的虚拟目录上的安全设置将生效。 它们不会更改以匹配您要部署的虚拟目录上。 在这种情况下，应该验证现有虚拟目录上的安全设置满足你的要求。  
  
> [!CAUTION]
>  如果虚拟目录使用 HTTPS （超文本传输协议通过安全套接字层） 协议，在导出期间，不保留其安全设置和导入它时，虚拟目录将继承根的安全设置。 应验证的安全设置满足你的要求。  
  
## <a name="prerequisites"></a>先决条件  
 若要执行本主题中的过程，您必须登录的成员帐户[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Administrators 组。 有关详细的权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。  
  
### <a name="to-add-a-virtual-directory-to-an-application"></a>若要将虚拟目录添加到应用程序  
  
1. 打开命令提示符，如下所示：单击**启动**，单击**运行**，类型`cmd`，然后单击**确定**。  
  
2. 键入以下命令，替换适当的值下, 表中所述：  
  
    **BTSTask AddResource** [/**应用程序名称：**<em>值</em>] **/Type:System.BizTalk:WebDirectory**[**/overwrite**]**/Source:**<em>值</em>[**/Destination:**<em>值</em>] [**/Server:** <em>值</em>] [**/database:**<em>值</em>]  
  
    例如：  
  
    **BTSTask AddResource /ApplicationName:MyApplication /Type:System.BizTalk:WebDirectory /Overwrite /Source:<http://Host1:90/MyVirtualDirectory> /Destination:<http://Host2:90/MyVirtualDirectory> /Server:MyDatabaseServer /Database:BizTalkMgmtDb**  
  
   |参数|ReplTest1|  
   |---------------|-----------|  
   |**/ApplicationName**|要将虚拟目录添加到 BizTalk 应用程序的名称。 如果未指定应用程序名称，则使用默认 BizTalk 应用程序组。 如果名称包含空格，则必须将其括在双引号 （"）。|  
   |**/Type**|**System.biztalk: webdirectory** （此值不区分大小写。）|  
   |**/Overwrite**|若要更新现有虚拟目录的选项。 如果未指定，且虚拟目录已存在具有相同的名称与要添加虚拟目录则 AddResources 操作将失败的应用程序中。|  
   |**/Source**|源虚拟目录的 URI。|  
   |**/ 目标**|从.msi 文件安装应用程序时要分配给虚拟目录的 URI。 如果未指定此参数，然后源参数的值用于 localhost 作为主机。|  
   |**/Server**|承载 BizTalk 管理数据库，在窗体 ServerName\InstanceName，端口中的 SQL Server 实例的名称。<br /><br /> 实例名称仅是所需的实例名称不同于服务器名称时。 端口是仅在 SQL Server 使用的端口号而不是默认 (1433) 时所需。<br /><br /> 示例：<br /><br /> Server=MyServer<br /><br /> Server=MyServer\MySQLServer,1533<br /><br /> 如果未提供，则使用本地计算机上运行的 SQL Server 实例的名称。|  
   |**/Database**|BizTalk 管理数据库的名称。 如果未指定，使用 SQL Server 的本地实例中运行的 BizTalk 管理数据库。|  
  
## <a name="see-also"></a>请参阅  
 [管理.NET 程序集、 证书和其他资源](../core/managing-net-assemblies-certificates-and-other-resources.md)   
 [AddResource 命令：虚拟目录](../core/addresource-command-virtual-directory.md)   
 [创建和修改 BizTalk 应用程序](../core/creating-and-modifying-biztalk-applications.md)