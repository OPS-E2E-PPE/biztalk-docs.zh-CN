---
title: 导出项目时，会发生什么情况 |Microsoft Docs
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
ms.openlocfilehash: 90ab32fb2931f8a0294356e94d9f80f29b5b7c84
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65258508"
---
# <a name="what-happens-when-artifacts-are-exported"></a>导出项目时，会发生什么情况
本主题介绍导出项目时，会发生什么情况。 有三种方法导出本主题中介绍的项目：  
  
-   将 BizTalk 应用程序及其项目导出到 BizTalk.msi （Windows 安装程序） 文件  
  
-   将策略导出到.xml 文件  
  
-   将绑定导出到.xml 文件  
  
## <a name="exporting-a-biztalk-application"></a>导出 BizTalk 应用程序  
 导出 BizTalk 应用程序和它包含的项目时，应用程序配置信息和项目数据导出到 BizTalk.msi 文件中。 大多数项目数据导出从 BizTalk 管理数据库，但存在以下例外：  
  
- 从组的规则引擎数据库导出策略的数据。  
  
- 如果不存在管理数据库中，从 Internet 信息服务 (IIS) 元数据库导出虚拟目录的数据。 虚拟目录尚未显式添加到应用程序时，会遇到这种情况 (如中所述[如何向应用程序添加虚拟目录](../core/how-to-add-a-virtual-directory-to-an-application.md)) 或应用程序已不导入此组从某一.msi 文件从其他 BizTalk 组导出。  
  
- 如果不存在管理数据库中，从本地计算机上的其他人证书存储导出证书数据。 该证书尚未显式添加到应用程序时，会遇到这种情况 (如中所述[如何将证书添加到应用程序](../core/how-to-add-a-certificate-to-an-application.md)) 或应用程序已不导入从.msi 文件时，此组从另一个 BizTalk 组中导出。 导出具有与之关联的证书的接收端口的应用程序时，将导出的证书。 从导出的证书删除私钥。  
  
  您可以使用此.msi 文件导入应用程序的项目，包括其所有数据，更改为另一个 BizTalk 组中的应用程序。 此外可以使用此.msi 文件的计算机上安装应用程序。  
  
## <a name="exporting-a-policy"></a>导出策略  
 当你使用管理控制台导出的 BizTalk 组或应用程序策略时，会生成包含策略信息的.xml 策略文件。 您可以导入此策略文件到另一个 BizTalk 组中创建的策略，以便组中的应用程序可以使用它。 此外可以通过使用 BTSTask 导出应用程序的策略信息。 BTSTask，但是，没有要导出策略.xml 文件的命令。 相反，您可以导出只包含该策略的应用程序.msi 文件。 您然后可以导入另一个组中的应用程序的.msi 文件。  
  
## <a name="exporting-bindings"></a>导出绑定  
 可以使用管理控制台或 BTSTask 导出 BizTalk 组、 应用程序或程序集的绑定。 当执行此操作时，BizTalk Server 将生成包含组、 应用程序或程序集的绑定信息的.xml 文件。 在导出绑定时，还可以导出全局参与方的组的信息。 然后，您可以将此绑定文件添加到应用程序或将其导入 BizTalk 组或应用程序。  
  
## <a name="see-also"></a>请参阅  
 [对项目采取的应用程序部署过程](../core/what-happens-to-artifacts-during-application-deployment.md)   
 [导出 BizTalk 应用程序、 绑定和策略](../core/exporting-biztalk-applications-bindings-and-policies.md)   
 [导入 BizTalk 应用程序、 绑定和策略](../core/importing-biztalk-applications-bindings-and-policies.md)   
 [如何将绑定文件添加到应用程序](../core/how-to-add-a-binding-file-to-an-application2.md)