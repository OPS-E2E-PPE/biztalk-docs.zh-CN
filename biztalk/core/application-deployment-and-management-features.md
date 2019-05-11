---
title: 应用程序部署和管理功能 |Microsoft Docs
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
ms.openlocfilehash: eb5258868e5c2c023be1a4a41f001b48d35a5c72
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65359091"
---
# <a name="application-deployment-and-management-features"></a>应用程序部署和管理功能
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 包括多个功能来帮助进行部署 BizTalk 业务解决方案：  
  
- **BizTalk 应用程序。** BizTalk 应用程序提供了一种查看和管理的项，称为"项目"组成 BizTalk 业务解决方案的方法。 项目包括程序集、 业务流程、 映射、 架构、 安全证书、 业务规则策略、 BAM 配置文件、 绑定、 脚本和是对函数所需的业务解决方案等。 可以将项目添加到 BizTalk 应用程序，然后查看、 打包、 部署和管理所有应用程序的项目作为单个实体中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。 您可以创建一个、 两个或更多的 BizTalk 应用程序来管理业务解决方案中的项目。 可以使用导出向导导出该应用程序及其项目，并将导入向导以便将.msi 文件导入其他 BizTalk 组以便那里重新创建它。 然后可以使用安装向导安装应用程序。 这些向导将在本主题后面所述。 在本文档中的每个部署过程包括有关使用管理控制台的说明。 您还可以使用 BTSTask 命令行工具来执行许多管理任务和本文档包括有关也使用 BTSTask 的过程。  
  
- **导入向导。** 使用导入向导，可从[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，将项目从.msi 文件导入 BizTalk 应用程序。 如果尚不存在指定的应用程序，则导入向导将创建它。 该向导还注册，并将项目存储在 BizTalk 管理数据库中的.msi 文件中。 使用导入向导导入项目的详细说明，请参阅[导入 BizTalk 应用程序、 绑定和策略](../core/importing-biztalk-applications-bindings-and-policies.md)。  
  
- **安装向导。** 可以启动安装向导作为导入向导的最后一步。 此向导将应用程序安装在本地计算机上，以便可以在本地计算机上运行应用程序。 有关说明，请参阅[导入 BizTalk 应用程序的方式](../core/how-to-import-a-biztalk-application.md)。 此外可以通过双击应用程序.msi 文件导入向导。 有关详细信息，请参阅[如何安装 BizTalk 应用程序](../core/how-to-install-a-biztalk-application.md)。  
  
- **导出向导。** 使用导出向导，也可从 BizTalk Server 管理控制台中，若要从 BizTalk 应用程序生成的.msi 文件。 然后可以使用导入向导将.msi 文件导入不同的 BizTalk 组。 这样可以轻松地将资源添加到应用程序，或新的 BizTalk 组上自动创建应用程序。 有关使用导出向导的详细信息，请参阅[如何导出 BizTalk 应用程序](../core/how-to-export-a-biztalk-application.md)。  
  
- **BTSTask 命令行工具。** BTSTask 支持的应用程序部署功能[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，您可以从命令行执行许多操作。 有关详细信息，请参阅[BTSTask 命令行参考](../core/btstask-command-line-reference.md)。  
  
  为了帮助你熟悉这些应用程序部署功能，我们建议你执行中的步骤[演练：部署基本 BizTalk 应用程序](../core/walkthrough-deploying-a-basic-biztalk-application.md)。  
  
## <a name="see-also"></a>请参阅  
 [了解 BizTalk 应用程序的部署和管理](../core/understanding-biztalk-application-deployment-and-management.md)