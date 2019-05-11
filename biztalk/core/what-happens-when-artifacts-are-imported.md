---
title: 导入项目时，会发生什么情况 |Microsoft Docs
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
ms.openlocfilehash: 52098eaa69fd2cefc25e6c7ba27908ec6a5a9bd9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395176"
---
# <a name="what-happens-when-artifacts-are-imported"></a>导入项目时，会发生什么情况
本主题介绍导入时，项目会发生什么情况。 有三种方式导入项目，本主题中介绍：  
  
-   将 BizTalk.msi 文件中的项目导入到 BizTalk 组或应用程序  
  
-   将.xml 策略文件导入到 BizTalk 组  
  
-   绑定文件导入到 BizTalk 组或应用程序  
  
## <a name="importing-a-biztalk-msi-file"></a>导入 BizTalk.msi 文件  
 您将 BizTalk.msi 文件导入到 BizTalk 组或应用程序时，BizTalk Server 处理的项目，它包含按如下所示：  
  
-   如果导入过程中添加的任何引用从此组中其他应用程序到应用程序，该引用添加到 BizTalk 管理数据库。  
  
-   如果指定此选项，应用程序中的现有项目将被覆盖的.msi 文件中的项目具有相同全名和版本号 （如果适用）。  
  
-   如果绑定文件已添加到应用程序，并导入过程中选择其目标环境，则应用绑定。  
  
-   配置为在导入时运行的预处理或后处理脚本将运行。  
  
-   序列化和 BizTalk 管理数据库中存储基于文件的项目数据。 其中包括针对程序集、 虚拟目录、 文件、 脚本、 证书和 BAM 项目的数据。  
  
    > [!IMPORTANT]
    >  出于安全考虑，私钥导出时将删除从每个证书中。 因此，没有专用密钥存储在 BizTalk 管理数据库。  
  
-   策略数据存储在规则引擎数据库。  
  
-   BAM 项目存储在 BAM 主导入数据库中。 部署 BAM 定义。  
  
-   BizTalk 程序集和已配置的"添加到 GAC 上导入"部署选项的.NET 程序集添加到全局程序集缓存 (GAC) 中。  
  
> [!NOTE]
>  由于项目数据存储在 BizTalk Server 数据库中，在更高版本导出到.msi 文件的应用程序时，BizTalk Server 可以检索的所有配置信息和数据与应用程序关联的数据库并将其项目并将其包含在.msi 文件中。 .Msi 文件导入到另一个 BizTalk 组中，会将所有项目配置信息和数据重新创建新组中。  
  
 导入应用程序后，可以查看、 管理和部署在一起作为单个实体或通过使用管理控制台或 BTSTask 单独的应用程序中的项目。 有关详细信息，请参阅[应用程序部署和管理工具](../core/application-deployment-and-management-tools.md)。  
  
## <a name="importing-a-policy"></a>导入策略  
 在从.xml 文件中导入策略，该策略添加到规则引擎数据库。 与导入 BizTalk.msi 文件内的策略时，该策略不是与 BizTalk 管理数据库中的任何应用程序相关联。 该策略的策略节点中显示\<的所有项目\>BizTalk Server 管理控制台中的文件夹。 导入策略后可以发布它，使其适用于应用程序中使用的组。 有关详细信息，请参阅[管理策略](../core/managing-policies.md)。  
  
## <a name="importing-a-binding-file"></a>导入绑定文件  
 绑定文件导入到 BizTalk 组中导入的文件具有相同的名称绑定的组中当前存在任何绑定的导入的文件中的绑定将覆盖并应用配置。  
  
 您将绑定文件导入 BizTalk 应用程序可以单独或作为应用程序的一部分，任何绑定当前中存在具有相同的名称，如文件中的绑定覆盖导入的绑定，该应用程序时，应用配置。  
  
> [!IMPORTANT]
>  出于安全原因，在导出绑定文件时 BizTalk Server 将从文件删除绑定密码。 导入绑定之后, 必须重新配置为发送端口的密码，并接收位置，它们才能正常。 发送端口在 BizTalk Server 管理控制台的传输属性对话框中配置密码，或接收位置。 有关说明，请参阅[如何创建发送端口](../core/how-to-create-a-send-port2.md)。 另请参阅[如何创建接收位置](../core/how-to-create-a-receive-location.md)。  
  
## <a name="see-also"></a>请参阅  
 [对项目采取的应用程序部署过程](../core/what-happens-to-artifacts-during-application-deployment.md)   
 [导入 BizTalk 应用程序、 绑定和策略](../core/importing-biztalk-applications-bindings-and-policies.md)   
 [依赖关系和应用程序部署](../core/dependencies-and-application-deployment.md)