---
title: 导入项目时，会发生什么情况 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- importing, artifacts
- artifacts, importing
ms.assetid: a83957df-6e16-419a-b693-87985b498cc4
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: aa252b520f985667820861403a46d39c8527ea07
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25974907"
---
# <a name="what-happens-when-artifacts-are-imported"></a>导入项目时发生的情况
本主题介绍导入项目时发生的情况。 可以通过本主题介绍的三种方式导入项目：  
  
-   将 BizTalk .msi 文件中的项目导入到 BizTalk 组或应用程序  
  
-   将 .xml 策略文件导入到 BizTalk 组  
  
-   将绑定文件导入到 BizTalk 组或应用程序  
  
## <a name="importing-a-biztalk-msi-file"></a>导入 BizTalk .msi 文件  
 将 BizTalk .msi 文件导入到 BizTalk 组或应用程序时，BizTalk Server 按如下所示处理它包含的项目：  
  
-   如果在导入期间您将任何引用从此应用程序添加到组中的其他应用程序，则该引用被添加到 BizTalk 管理数据库。  
  
-   如果指定此选项，则应用程序中的现有项目被 .msi 文件中具有相同全名和版本号（如果适用）的项目覆盖。  
  
-   如果绑定文件已添加到应用程序，并且您在导入期间选择其目标环境，则应用绑定。  
  
-   配置为在导入时运行的预处理或后处理脚本将运行。  
  
-   基于文件的项目数据被序列化，存储在 BizTalk 管理数据库中。 其中包括程序集、虚拟目录、文件、脚本、证书和 BAM 项目。  
  
    > [!IMPORTANT]
    >  出于安全考虑，私钥在导出时从每个证书中删除。 因此，在 BizTalk 管理数据库中不存储私钥。  
  
-   策略数据存储在规则引擎数据库中。  
  
-   BAM 项目存储在 BAM 主导入数据库中。 BAM 定义部署。  
  
-   配置了“导入时添加到 GAC”部署选项的 BizTalk 程序集和 .NET 程序集添加到全局程序集引擎 (GAC)。  
  
> [!NOTE]
>  项目数据存储在 BizTalk Server 数据库中，因此，当您稍后将应用程序导出到 .msi 文件中时，BizTalk Server 可以从数据库中检索所有配置信息以及与应用程序及其项目关联的数据，并将这些信息和数据包括在 .msi 文件中。 当您将 .msi 文件导入另一个 BizTalk 组时，所有项目配置信息和数据在新组中重新创建。  
  
 导入应用程序后，您可以使用管理控制台或 BTSTask 在应用程序中将多个项目作为单个实体一起进行查看、管理和部署，也可以对项目分别进行查看、管理和部署。 有关详细信息，请参阅[应用程序部署和管理工具](../core/application-deployment-and-management-tools.md)。  
  
## <a name="importing-a-policy"></a>导入策略  
 从 .xml 文件导入策略时，该策略被添加到规则引擎数据库。 与您导入 BizTalk .msi 文件内的策略不同的是，该策略不与 BizTalk 管理数据库中的任何应用程序相关联。 策略中的策略节点显示\<所有项目\>BizTalk Server 管理控制台中的文件夹。 导入策略后，您可以发布它，使其对组中的应用程序可用。 有关详细信息，请参阅[管理策略](../core/managing-policies.md)。  
  
## <a name="importing-a-binding-file"></a>导入绑定文件  
 将绑定文件导入 BizTalk 组时，在该组中当前存在的与所导入文件中的绑定同名的任何绑定被所导入文件中的绑定覆盖，并应用其配置。  
  
 将绑定文件分别或作为应用程序的一部分导入 BizTalk 应用程序时，在应用程序中当前存在的与文件中的绑定同名的任何绑定被导入的绑定覆盖，并应用其配置。  
  
> [!IMPORTANT]
>  出于安全方面的原因，如果导出绑定文件，BizTalk Server 会从该文件中删除绑定的密码。 在导入绑定后，必须为发送端口和接收位置重新配置密码，它们才能正常运行。 您需要在 BizTalk Server 管理控制台的“传输属性”对话框中为发送端口或接收位置配置密码。 有关说明，请参阅[如何创建发送端口](../core/how-to-create-a-send-port2.md)。 另请参阅[如何创建接收位置](../core/how-to-create-a-receive-location.md)。  
  
## <a name="see-also"></a>另请参阅  
 [会发生什么情况项目在应用程序部署过程](../core/what-happens-to-artifacts-during-application-deployment.md)   
 [导入 BizTalk 应用程序、 绑定和策略](../core/importing-biztalk-applications-bindings-and-policies.md)   
 [依赖关系和应用程序部署](../core/dependencies-and-application-deployment.md)