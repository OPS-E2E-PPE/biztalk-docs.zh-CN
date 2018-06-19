---
title: 导出项目时，会发生什么情况 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- exporting, artifacts
- artifacts, exporting
ms.assetid: accc9a81-01fb-4da7-a5a5-167835d393a2
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d92a65889ea642706ae5c51849748fd8ad085a02
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22289381"
---
# <a name="what-happens-when-artifacts-are-exported"></a>导出项目时发生的情况
本主题介绍导出项目时发生的情况。 可以通过本主题介绍的三种方式导出项目：  
  
-   将 BizTalk 应用程序及其项目导出到 BizTalk .msi (Windows Installer) 文件中  
  
-   将策略导出到 .xml 文件中  
  
-   将绑定导出到 .xml 文件中  
  
## <a name="exporting-a-biztalk-application"></a>导出 BizTalk 应用程序  
 在导出某一 BizTalk 应用程序以及它所包含的项目时，应用程序配置信息和项目数据将导出到 BizTalk .msi 文件中。 大多数项目数据都会从 BizTalk 管理数据库导出，但存在以下例外：  
  
-   策略数据从组的规则引擎数据库中导出。  
  
-   虚拟目录数据从 Internet 信息服务 (IIS) 元数据库导出（如果在管理数据库中不存在这些数据）。 这将出现这种情况的虚拟目录尚未显式添加到应用程序 (如中所述[如何将虚拟目录添加到应用程序](../core/how-to-add-a-virtual-directory-to-an-application.md)) 或应用程序已不导入此组从.msi 文件从另一个 BizTalk 组导出。  
  
-   证书数据从本地计算机上的其他人证书存储导出（如果在管理数据库中不存在证书数据）。 证书尚未显式添加到应用程序时，会遇到这种情况 (如中所述[如何将证书添加到应用程序](../core/how-to-add-a-certificate-to-an-application.md)) 或应用程序已不导入从.msi 文件的此组从另一个 BizTalk 组导出。 在应用程序与证书与之关联的接收端口一起导出时，将导出证书。 在导出时私钥将会从证书中删除。  
  
 您可以使用此 .msi 文件将应用程序的项目（包括其所有数据）导入到其他 BizTalk 组的应用程序中。 您还可以使用此 .msi 文件在计算机上安装应用程序。  
  
## <a name="exporting-a-policy"></a>导出策略  
 在您使用管理控制台导出某一 BizTalk 组或应用程序的策略时，它将生成包含该策略信息的一个 .xml 策略文件。 您可以将该策略文件导入到其他 BizTalk 组中以在那里创建策略，以便该组中的应用程序可以使用该策略。 您还可以通过使用 BTSTask 导出应用程序的策略信息。 但是，BTSTask 不具有用于导出策略 .xml 文件的命令。 您而是可以导出只包含该策略的应用程序 .msi 文件。 然后，可以将该 .msi 文件导入到另一个组的应用程序中。  
  
## <a name="exporting-bindings"></a>导出绑定  
 您可以使用管理控制台或 BTSTask 为 BizTalk 组、应用程序或程序集导出绑定。 这样做了之后，BizTalk Server 将生成一个 .xml 文件，包含该组、应用程序或程序集的绑定信息。 在您导出绑定时，还可以导出该组的全局参与方信息。 然后，您可以将此绑定文件添加到某一应用程序中，或将它导入到某一 BizTalk 组或应用程序中。  
  
## <a name="see-also"></a>另请参阅  
 [会发生什么情况项目在应用程序部署过程](../core/what-happens-to-artifacts-during-application-deployment.md)   
 [导出 BizTalk 应用程序、 绑定和策略](../core/exporting-biztalk-applications-bindings-and-policies.md)   
 [导入 BizTalk 应用程序、 绑定和策略](../core/importing-biztalk-applications-bindings-and-policies.md)   
 [如何将绑定文件添加到应用程序](../core/how-to-add-a-binding-file-to-an-application2.md)