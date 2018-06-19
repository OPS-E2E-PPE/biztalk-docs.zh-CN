---
title: 如何将证书添加到应用程序 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- applications, certificates
- managing [certificates], adding to applications
- certificates, applications
- managing [applications], certificates
- managing [certificates], applications
- managing [resources], certificates
ms.assetid: 7c615002-6627-4134-9c2b-bf1c89d626c2
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7551e18b1e63f706dfe7e5ff8f951e7aee4f4694
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22248173"
---
# <a name="how-to-add-a-certificate-to-an-application"></a>如何向应用程序添加证书
本主题说明如何使用命令行向 BizTalk Server 应用程序添加证书。 此选项在 BizTalk Server 管理控制台中不可用。 您向某一 BizTalk 应用程序添加证书，以便可以将证书从一个 BizTalk 组传输到另一个组中，与应用程序打包在一起。 您使用证书来验证凭据并为发送端口和接收位置建立安全的链接。 有关详细信息，请参阅[如何将证书分配给发送端口](../core/how-to-assign-a-certificate-to-a-send-port.md)和[如何将证书分配给接收位置](../core/how-to-assign-a-certificate-to-a-receive-location.md)。  
  
 向应用程序中添加证书时，请切记以下几点：  
  
-   在将某一证书添加到应用程序时，该证书将作为证书项目添加到 BizTalk 管理数据库中。 在您安装该应用程序时，该证书将导入到本地计算机上的“其他人”证书存储中；因此，在您将证书分配给某一发送端口或接收位置前，可能无需执行额外的步骤来将证书导入到此证书存储中。 在您使用 BTSTask 来添加证书时，该证书必须存在于“其他人”证书存储中，并且必须指定其指纹。  
  
    > [!NOTE]
    >  在导出某一证书时，私钥将被删除。 在安装应用程序时，尽管证书将导入证书存储中，但它不能用于解密已加密的消息，虽然它可用于发送已加密的消息。 如果您出于前述目的需要使用证书，则应在使用该证书的发送端口的宿主计算机上，在“其他人”证书存储中重新安装该证书。  
  
-   作为一种最佳实践，如果某个证书将由两个或多个应用程序中的发送端口或接收位置使用，应将该证书部署在一个单独的应用程序中，然后从需要使用该证书的应用程序中引用该应用程序。 这是因为 BizTalk 组中只能有一个证书具有特定的指纹，因此您不能将同一个证书导入到两个不同的应用程序中。 如果尝试导入两个使用同一证书的应用程序，则第一个导入将会成功，而第二个导入将会失败。 在这种情况下，使用“覆盖”导入选项并不能解决问题，因为您要覆盖的现有证书包含在另一个应用程序中。  
  
## <a name="prerequisites"></a>先决条件  
 若要执行本主题中的过程，必须使用 BizTalk Server Administrators 组的成员帐户登录。 有关更多详细权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。  
  
### <a name="to-add-a-certificate-to-an-application"></a>向应用程序添加证书  
  
1.  如下所示打开命令提示符： 单击**启动**，单击**运行**，类型`cmd`，然后单击**确定**。  
  
2.  键入以下命令，替换为适当的值下, 表中所述：  
  
     **BTSTask AddResource** [**/ApplicationName:***值*] **/Type:System.BizTalk:Certificate** [**/Overwrite**] **/Thumbprint:"***值***"** [**/Server:***值*] [**/数据库：***值*]  
  
     例如：  
  
     **BTSTask AddResource /ApplicationName:MyApplication /Type:System.BizTalk:Certificate /Overwrite /Thumbprint:"04 a2 8e 32 24 f9 36 b9 42 81 12 71 3a d2 ef db c7 9c 83 dc"/Server:MyDatabaseServer /Database:BizTalkMgmtDb**  
  
    |参数|值|  
    |---------------|-----------|  
    |**/ 应用程序名称**|向其添加证书的 BizTalk 应用程序的名称。 如果未指定应用程序名称，则使用组的默认 BizTalk 应用程序。 如果名称包含空格，必须将它括在双引号 （"）。|  
    |**/ 类型**|**System.BizTalk:Certificate** （此值不区分大小写。）|  
    |**/ 覆盖**|更新现有证书的选项。 如果未指定，且应用程序中已存在与要添加的证书具有相同 Thumbprint 属性的证书，则 Add 操作将失败。 通过在证书管理单元中双击证书，再单击“详细信息”选项卡，可以查看它的 Thumbprint 属性。有关详细信息，请参阅证书管理单元文档中的“查看证书信息”。|  
    |**/ 指纹**|该证书指纹属性 (*指纹*是数据的摘要)。 此值必须放在双引号 (") 中。|  
    |**/ 服务器**|BizTalk 管理数据库的宿主 SQL Server 实例的名称，格式为“服务器名称\实例名称,端口”。<br /><br /> 只在实例名称与服务器名称不相同时才需要指定实例名称。 只在 SQL Server 不使用默认端口号 (1433) 时才需要指定端口。<br /><br /> 示例：<br /><br /> Server=MyServer<br /><br /> Server=MyServer\MySQLServer,1533<br /><br /> 如果未提供，则使用本地计算机上运行的 SQL Server 实例的名称。|  
    |**/ 数据库**|BizTalk 管理数据库的名称。 如果未指定，则使用在本地 SQL Server 实例中运行的 BizTalk 管理数据库。|  
  
## <a name="see-also"></a>另请参阅  
 [管理.NET 程序集、 证书和其他资源](../core/managing-net-assemblies-certificates-and-other-resources.md)   
 [AddResource 命令： 证书](../core/addresource-command-certificate.md)   
 [创建和修改 BizTalk 应用程序](../core/creating-and-modifying-biztalk-applications.md)