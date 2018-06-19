---
title: 应用程序部署安全建议 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- security, applications
- best practices, applications
- best practices, security
- security, best practices
- applications, best practices
- applications, security
ms.assetid: 77902140-8b4c-437c-af4c-10a12b3bc950
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9a0402ef23de70150d541dfd672d2af7efe3a924
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22231949"
---
# <a name="application-deployment-security-recommendations"></a>应用程序部署的安全建议
下面是在您的环境中部署 BizTalk 应用程序时应遵守的一些准则：  
  
-   将应用程序导出到某一 .msi 文件时，会从文件和文件夹中删除所有随机访问控制列表 (DACL)。 从该 .msi 文件安装应用程序后，必须对文件和文件夹重新配置所有的安全设置。  
  
-   出于安全方面的原因，如果导出绑定文件，BizTalk Server 会从该文件中删除绑定的密码。 在导入绑定后，必须为发送端口和接收位置重新配置密码，它们才能正常运行。 您需要在 BizTalk Server 管理控制台的“传输属性”对话框中为发送端口或接收位置配置密码。 有关说明，请参阅[如何创建发送端口](../core/how-to-create-a-send-port2.md)。 另请参阅[如何创建接收位置](../core/how-to-create-a-receive-location.md)。 有关绑定文件的详细信息，请参阅[绑定文件和应用程序部署](../core/binding-files-and-application-deployment.md)。  
  
-   部署或取消部署属性架构可能会暴露敏感数据，进而在跟踪中暴露敏感信息。 只要部署或取消部署包含属性架构的程序集，事件查看器就会在 Windows 应用程序事件日志中记录该事件。 您应该在事件日志中检查这些消息，以确保所有程序集部署活动均符合您的敏感数据策略。  
  
     事件日志中生成的部署消息为：  
  
     **用户"{1}"部署的程序集"{0}"包含属性的架构。**  
  
     事件日志中生成的取消部署消息为：  
  
     **用户"{1}"已取消部署的程序集"{0}"包含属性的架构。**  
  
-   如果应用程序包含虚拟目录则需要注意：虚拟目录的安全设置是在应用程序导出期间生成 .msi 文件时起作用的那些设置。 如果要向生产环境中部署应用程序，则在导出应用程序之前，应验证设置满足安全要求。  
  
     不过，如果您部署包含某一虚拟目录的应用程序，并且目标环境中已经存在该虚拟目录，现有虚拟目录的安全设置将生效。 它们不会被更改以匹配您部署的虚拟目录的安全设置。 您应该验证现有虚拟目录的安全设置是否满足您的要求。  
  
    > [!CAUTION]
    >  如果虚拟目录使用 HTTPS（安全超文本传输协议）协议，则在导出期间不会保留其安全设置，进行导入时，虚拟目录将继承根的安全设置。 您应该验证安全设置是否满足您的要求。  
  
-   如果为某一 Web Services 指定的应用程序池在您导入应用程序时不存在，则使用默认应用程序池。 默认应用程序池上的安全设置可能不适合您的要求。 因此，我们建议您或者在导入应用程序前创建应用程序池并配置适当的安全设置，或者验证默认应用程序池上的设置是否适当。  
  
-   请确保您信任所部署的 Windows Installer (.msi) 文件的来源，以便避免可能由恶意 .msi 文件创建者造成的安全问题。 有关详细信息，请参阅[安全和 Windows Installer](../core/security-and-windows-installer.md)。  
  
-   请确保您有权部署应用程序。 有关详细信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。  
  
-   请确保只有 BizTalk 管理员才能访问程序集、绑定文件和策略文件，因为它们可能包含连接和配置信息之类的重要业务数据。 如果您通过网络共享部署应用程序，则在网络共享上配置随机访问控制列表 (DACL)，以便只有 BizTalk 管理员才能查看其内容。 有关组和用户帐户的详细信息，请参阅[Windows 组和 BizTalk Server 中的用户帐户](../core/windows-groups-and-user-accounts-in-biztalk-server.md)。  
  
-   在您执行部署操作时，BizTalk Server 将与 BizTalk 管理数据库通信。 如果在它们之间存在某一防火墙，则必须打开处理、服务和数据域之间的防火墙上的适当端口。 有关详细信息，请参阅[的 BizTalk Server 所需端口](../core/required-ports-for-biztalk-server.md)。  
  
-   如果您指向可能包含敏感数据的某一程序集、绑定文件或其他资源文件的远程位置，则应考虑源计算机和您从其执行部署的计算机之间的网络安全性。 如果这两台计算机之间的网络没有完全与潜在的攻击者隔离，则您应将目标文件复制到可移动媒体上，并将其物理传输到您要执行部署的计算机上。  
  
## <a name="see-also"></a>另请参阅  
 [应用程序部署的安全注意事项](../core/security-considerations-for-application-deployment.md)