---
title: 如何将证书添加到应用程序 |Microsoft Docs
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
ms.openlocfilehash: a391759b0a05d4266e38ae0eed6d25fded834f0d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65343970"
---
# <a name="how-to-add-a-certificate-to-an-application"></a>如何将证书添加到应用程序
本主题介绍如何使用命令行来将证书添加到 BizTalk 应用程序。 此选项不在 BizTalk Server 管理控制台中可用。 将证书添加到 BizTalk 应用程序，以便可以传输到另一个，与应用程序打包在一起的证书从一个 BizTalk 组。 若要验证标识，并建立安全链接，了解发送端口和接收位置使用的证书。 有关详细信息，请参阅[如何为发送端口分配证书](../core/how-to-assign-a-certificate-to-a-send-port.md)并[如何将证书分配到接收位置](../core/how-to-assign-a-certificate-to-a-receive-location.md)。  
  
 当将证书添加到应用程序，请记住以下重要事项：  
  
-   时将证书添加到应用程序，该证书作为证书项目添加到 BizTalk 管理数据库。 在安装应用程序时，证书将导入本地计算机上的其他人证书存储，因此可能不需要执行额外的导入此存储可以将其分配给发送端口或接收位置之前的步骤。 当使用 BTSTask 来添加证书时，证书必须存在于其他人证书存储，并且必须指定其指纹。  
  
    > [!NOTE]
    >  导出证书后，会删除私钥。 安装应用程序时，尽管将证书导入的证书存储区，它不能用于解密已加密的邮件，尽管它可以用来发送加密的消息。 如果需要对前一种用途使用的证书，应在宿主使用的证书的发送端口的计算机上的其他人证书存储中重新安装它。  
  
-   最佳做法是，如果证书将由发送端口或接收位置在两个或多个应用程序中，您应将不同的应用程序，该证书部署，然后从需要使用证书的应用程序中引用此应用程序。 这是因为只有一个具有特定的指纹的证书可以存在于 BizTalk 组中，因此你将不能导入两个不同的应用程序中的相同证书。 如果你尝试导入每个使用相同的证书的两个应用程序，第一个导入将成功，并且第二个将不会。 在这种情况下，使用覆盖导入选项未更正问题，如你想要覆盖现有证书包含在另一个应用程序。  
  
## <a name="prerequisites"></a>先决条件  
 若要执行本主题中的过程，必须是 BizTalk Server Administrators 组的成员的帐户登录。 有关详细的权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。  
  
### <a name="to-add-a-certificate-to-an-application"></a>若要将证书添加到应用程序  
  
1. 打开命令提示符，如下所示：单击**启动**，单击**运行**，类型`cmd`，然后单击**确定**。  
  
2. 键入以下命令，替换适当的值下, 表中所述：  
  
    **BTSTask AddResource** [**/ApplicationName:**<em>值</em>] **/Type:System.BizTalk:Certificate** [**/overwrite**]**/Thumbprint:"**<em>值</em>**"** [**/Server:**<em>值</em>] [**/数据库：**<em>值</em>]  
  
    例如：  
  
    **BTSTask AddResource /ApplicationName:MyApplication /Type:System.BizTalk:Certificate /Overwrite /Thumbprint:"04 a2 8e 32 24 f9 36 b9 42 81 12 71 3a d2 ef db c7 9 c 83 dc"/Server:MyDatabaseServer /Database:BizTalkMgmtDb**  
  
   |参数|ReplTest1|  
   |---------------|-----------|  
   |**/ApplicationName**|要将证书添加到 BizTalk 应用程序的名称。 如果未指定应用程序名称，则使用默认 BizTalk 应用程序组。 如果名称包含空格，则必须将其括在双引号 （"）。|  
   |**/Type**|**System.biztalk: certificate** （此值不区分大小写。）|  
   |**/Overwrite**|若要更新现有证书的选项。 如果未指定，且证书已存在具有相同 Thumbprint 属性为要添加，则添加操作将失败的证书的应用程序中。 可以通过双击证书管理单元中的证书，然后单击详细信息选项卡查看指纹属性。有关详细信息，请参阅"查看证书信息"文档中的证书管理单元中。|  
   |**/Thumbprint**|证书的指纹属性 (*指纹*是数据的摘要)。 此值必须括在双引号 （"）。|  
   |**/Server**|承载 BizTalk 管理数据库，在窗体 ServerName\InstanceName，端口中的 SQL Server 实例的名称。<br /><br /> 实例名称仅是所需的实例名称不同于服务器名称时。 端口是仅在 SQL Server 使用的端口号而不是默认 (1433) 时所需。<br /><br /> 示例：<br /><br /> Server=MyServer<br /><br /> Server=MyServer\MySQLServer,1533<br /><br /> 如果未提供，则使用本地计算机上运行的 SQL Server 实例的名称。|  
   |**/Database**|BizTalk 管理数据库的名称。 如果未指定，使用 SQL Server 的本地实例中运行的 BizTalk 管理数据库。|  
  
## <a name="see-also"></a>请参阅  
 [管理.NET 程序集、 证书和其他资源](../core/managing-net-assemblies-certificates-and-other-resources.md)   
 [AddResource 命令：证书](../core/addresource-command-certificate.md)   
 [创建和修改 BizTalk 应用程序](../core/creating-and-modifying-biztalk-applications.md)