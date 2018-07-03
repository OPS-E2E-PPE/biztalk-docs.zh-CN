---
title: 如何将绑定导入 BizTalk 应用程序 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- bindings, applications
- applications, importing
- applications, bindings
- bindings, importing
ms.assetid: 89841b23-4e1b-46ff-8f00-cdad65d6216d
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 174a54b5f1ad98b4ba57c70a24ec2f621577271d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37011942"
---
# <a name="how-to-import-bindings-into-a-biztalk-application"></a>如何将绑定导入 BizTalk 应用程序
本主题介绍如何使用 BizTalk Server 管理控制台或命令行将绑定从 .xml 文件导入 BizTalk 应用程序。 您还可以导入绑定到 BizTalk 组，如中所述[如何将绑定导入到 BizTalk 组](../core/how-to-import-bindings-into-a-biztalk-group.md)。  
  
 您可导入已经从程序集、应用程序或组中导出的绑定。 如果要导入组绑定，则只有同名的应用程序绑定应用到绑定所导入到的应用程序。 您还可从具有不同名称的应用程序导入绑定。 有关导出绑定的说明，请参阅[导出绑定](../core/exporting-bindings6.md)。  
  
## <a name="prerequisites"></a>必要條件  
 若要执行本主题中的过程，必须是 BizTalk Server Administrators 组的成员的帐户登录。 有关详细的权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。  
  
## <a name="to-import-bindings-into-a-biztalk-application"></a>将绑定导入到 BizTalk 应用程序  
  
#### <a name="using-the-biztalk-server-administration-console"></a>使用 BizTalk Server 管理控制台  
  
1. 单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2. 在控制台树中，依次展开“[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]”、“BizTalk 组”和“应用程序”。  
  
3. 右键单击您要向其中导入绑定，指向应用的程序**导入**，然后单击**绑定**。  
  
4. 单击绑定文件，然后单击**打开**。  
  
    绑定文件中的项目将写入该应用程序中。 这些项目显示在该应用程序的相应文件夹中。  
  
#### <a name="using-the-command-line"></a>使用命令行  
  
1. 按如下所示打开命令提示符： 单击**启动**，单击**运行**，类型`cmd`，然后单击**确定**。  
  
2. 键入以下命令，替换适当的值下, 表中所述：  
  
    **BTSTask ImportBindings /Source:** *值*[**/ApplicationName:**<em>值</em>] [**/Server:** <em>值</em>] [**/database:**<em>值</em>]  
  
    例如，以下命令将绑定导入到默认 BizTalk 组下名为 MyApplication 的应用程序中。  
  
    **BTSTask ImportBindings /ApplicationName:MyApplication** /**Source:C:\Bindings\Binding1.xml**  
  
   |参数|ReplTest1|  
   |---------------|-----------|  
   |**/ 源**|要导入的绑定文件的完整路径，包含文件名。 包含空格的路径必须放在引号 (") 中。|  
   |**/ 应用程序名称**|绑定要导入到的 BizTalk 应用程序的名称。 该应用程序必须存在，否则导入操作将失败。 如果未指定此参数，则使用默认 BizTalk 应用程序。 包含空格的应用程序名必须放在引号 (") 中。|  
   |**/ 服务器**|BizTalk 管理数据库的宿主 SQL Server 实例的名称，格式为“服务器名称\实例名称,端口”。<br /><br /> 只在实例名称与服务器名称不相同时才需要指定实例名称。 只在 SQL Server 不使用默认端口号 (1433) 时才需要指定端口。<br /><br /> 示例：<br /><br /> Server=MyServer<br /><br /> Server=MyServer\MySQLServer,1533<br /><br /> 如果未提供，则使用本地计算机上运行的 SQL Server 实例的名称。|  
   |**/ 数据库**|BizTalk 管理数据库的名称。 如果未指定，则使用在本地 SQL Server 实例中运行的 BizTalk 管理数据库。|  
  
## <a name="see-also"></a>请参阅  
 [导入 BizTalk 应用程序、 绑定和策略](../core/importing-biztalk-applications-bindings-and-policies.md)   
 [ImportBindings 命令](../core/importbindings-command.md)