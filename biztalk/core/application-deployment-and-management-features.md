---
title: 应用程序部署和管理功能 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- what's new, Installation Wizard
- what's new, BTSTask command-line tool
- what's new, Import Wizard
- deploying, what's new
- what's new, Export Wizard
- what's new, deploying
- applications, what's new
- what's new, applications
ms.assetid: 2d09d6b1-1003-406f-81da-14e21a1cbc81
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6e0be112d97c5ef17c3d9d99fbb22ea59b17e482
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22231037"
---
# <a name="application-deployment-and-management-features"></a>应用程序部署和管理功能
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 包括可帮助部署 BizTalk 业务解决方案的多个功能：  
  
-   **BizTalk 应用程序。** BizTalk 应用程序使您能够查看和管理的项，称为"项目"构成 BizTalk 业务解决方案。 项目包括业务解决方案正常运行所必需的程序集、业务流程、映射、架构、安全证书、业务规则策略、BAM 配置文件、绑定和脚本等。 您可以将项目添加到某一 BizTalk 应用程序，然后从 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台内将该应用程序的所有项目作为单个实体查看、打包、部署和管理。 您可以创建一个、两个或多个 BizTalk 应用程序，以便管理业务解决方案中的各个项目。 您可以使用导出向导导出该应用程序及其项目，然后使用导入向导将 .msi 文件导入到其他 BizTalk 组以便在那里重新创建它。 然后，您可以使用安装向导安装该应用程序。 本主题后面的部分对这些向导进行了介绍。 本文档中的每个部署过程都包括了有关使用管理控制台的说明。 您还可以使用 BTSTask 命令行工具来执行许多管理任务，并且本文档也包括有关使用 BTSTask 的过程。  
  
-   **导入向导。** 使用导入向导，可从[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，若要将项目从.msi 文件导入到 BizTalk 应用程序。 如果指定的应用程序不存在，则导入向导将自动创建该程序。 该向导还注册项目并将项目存储在 BizTalk 管理数据库的 .msi 文件中。 有关使用导入向导导入项目的详细说明，请参阅[导入 BizTalk 应用程序、 绑定和策略](../core/importing-biztalk-applications-bindings-and-policies.md)。  
  
-   **安装向导。** 您可以启动安装向导作为导入向导的最后一步。 此向导将在本地计算机上该安装应用程序，以便您可以在本地计算机上运行该应用程序。 有关说明，请参阅[如何导入 BizTalk 应用程序](../core/how-to-import-a-biztalk-application.md)。 您还可以通过双击应用程序 .msi 文件启动导入向导。 有关详细信息，请参阅[如何安装 BizTalk 应用程序](../core/how-to-install-a-biztalk-application.md)。  
  
-   **导出向导。** 您使用在 BizTalk Server 管理控制台中还提供的导出向导，根据 BizTalk 应用程序生成某一 .msi 文件。 然后，您可以使用导入向导将该 .msi 文件导入不同的 BizTalk 组。 这可以便于向应用程序添加资源，或者可以在新的 BizTalk 组上自动创建应用程序。 有关使用导出向导的详细信息，请参阅[how to Export BizTalk 应用程序如何](../core/how-to-export-a-biztalk-application.md)。  
  
-   **BTSTask 命令行工具。** BTSTask 支持的应用程序部署功能[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，从而可以从命令行执行许多操作。 有关详细信息，请参阅[BTSTask 命令行参考](../core/btstask-command-line-reference.md)。  
  
 为了帮助你熟悉这些应用程序部署功能，我们建议你执行中的步骤[演练： 将基本的 BizTalk 应用程序部署](../core/walkthrough-deploying-a-basic-biztalk-application.md)。  
  
## <a name="see-also"></a>另请参阅  
 [了解 BizTalk 应用程序部署和管理](../core/understanding-biztalk-application-deployment-and-management.md)