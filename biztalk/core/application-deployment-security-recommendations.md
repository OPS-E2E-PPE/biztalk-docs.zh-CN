---
title: 应用程序部署的安全建议 |Microsoft Docs
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
ms.openlocfilehash: 0ea901fdc44887d92d221af6e737aa133943b14d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65359071"
---
# <a name="application-deployment-security-recommendations"></a>应用程序部署的安全建议
以下是部署在环境中的 BizTalk 应用程序的准则：  
  
-   应用程序导出到.msi 文件时，将从文件和文件夹中删除所有随机访问控制列表 (Dacl)。 从.msi 文件安装应用程序之后, 必须重新配置的文件和文件夹上的所有安全设置。  
  
-   出于安全原因，在导出绑定文件时 BizTalk Server 将从文件删除绑定密码。 导入绑定之后, 必须重新配置为发送端口的密码，并接收位置，它们才能正常。 发送端口在 BizTalk Server 管理控制台的传输属性对话框中配置密码，或接收位置。 有关说明，请参阅[如何创建发送端口](../core/how-to-create-a-send-port2.md)。 另请参阅[如何创建接收位置](../core/how-to-create-a-receive-location.md)。 有关绑定文件的详细信息，请参阅[绑定文件和应用程序部署](../core/binding-files-and-application-deployment.md)。  
  
-   部署或取消部署属性架构可能暴露敏感数据，并随后暴露在跟踪的敏感信息。 每当部署或已取消部署包含属性架构的程序集时，事件查看器记录的事件在 Windows 应用程序事件日志中。 应检查这些消息，以确保所有程序集部署活动均符合你的策略的任何敏感数据在事件日志。  
  
     部署的事件日志中生成的消息为：  
  
     **用户"{1}"已部署程序集"{0}"包含属性架构。**  
  
     取消部署事件日志中生成的消息为：  
  
     **用户"{1}"已取消部署程序集"{0}"包含属性架构。**  
  
-   如果应用程序中包括虚拟目录，请注意，虚拟目录上的安全设置是生效时的那些应用程序导出期间生成.msi 文件。 如果要部署到生产环境中，应用程序，然后导出该应用程序，则应验证设置满足安全要求。  
  
     如果，但是，部署的应用程序中包括虚拟目录，并在目标环境中，已存在虚拟目录上的现有虚拟目录的安全设置将生效。 它们不会更改以匹配您要部署的虚拟目录上。 您应该验证现有虚拟目录上的安全设置满足你的要求。  
  
    > [!CAUTION]
    >  如果虚拟目录使用 HTTPS （超文本传输协议通过安全套接字层） 协议，在导出期间，不保留其安全设置和导入它时，虚拟目录将继承根的安全设置。 应验证的安全设置满足你的要求。  
  
-   如果指定的 Web 服务的应用程序池不存在时导入应用程序，则使用默认应用程序池。 默认应用程序池上的安全设置可能不适合你的要求。 因此，我们建议你创建的应用程序池并导入应用程序之前配置适当的安全设置，或验证默认应用程序池上的设置适用。  
  
-   请确保您信任的 Windows Installer (.msi) 文件的部署以避免可能由恶意.msi 文件创建者造成的安全问题源。 有关详细信息，请参阅[安全性和 Windows 安装程序](../core/security-and-windows-installer.md)。  
  
-   请确保您有权部署应用程序。 有关详细信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。  
  
-   确保只有 BizTalk 管理员才有权访问程序集、 绑定文件和策略文件，因为它们可能包含连接和配置信息之类的关键业务数据。 如果你部署应用程序通过网络共享，配置网络共享上的自由访问控制列表 (DACL)，以便只有 BizTalk 管理员可以查看其内容。 有关组和用户帐户的详细信息，请参阅[Windows 组和 BizTalk Server 中的用户帐户](../core/windows-groups-and-user-accounts-in-biztalk-server.md)。  
  
-   在执行部署操作时，BizTalk Server 与 BizTalk 管理数据库通信。 如果它们之间存在防火墙，则必须打开处理、 服务和数据域之间的防火墙上相应的端口。 有关详细信息，请参阅[的 BizTalk Server 所需端口](../core/required-ports-for-biztalk-server.md)。  
  
-   如果您指向远程位置的程序集、 绑定文件或其他资源文件，可能包含敏感数据，则应考虑源计算机和运行部署的计算机之间的网络安全。 如果这两台计算机之间的网络不是与潜在攻击者完全隔离的应将目标文件复制到可移动介质，并以物理方式将其传输到运行部署的计算机。  
  
## <a name="see-also"></a>请参阅  
 [应用程序部署的安全注意事项](../core/security-considerations-for-application-deployment.md)