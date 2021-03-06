---
title: 应用程序部署任务 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- applications, deploying
- applications, tasks
- deploying [applications], tasks
ms.assetid: 8cb29292-9868-41fa-9f2c-d1c20dfdddbb
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: da4c55063132a7115eba0f81efb5ede5c4f24df6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65359060"
---
# <a name="application-deployment-tasks"></a>应用程序部署任务
在本部分中的主题提供有关所涉及的应用程序部署过程的每个阶段的以下任务的详细信息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:  
  
1. **开发。** 开发人员部署包括在从 BizTalk 应用程序中的 BizTalk 程序集[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]到[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]开发计算机上运行。 这会自动创建应用程序，并使用包含在程序集中的项目填充它。 项目是所有构成 BizTalk 业务解决方案，包括 BizTalk 程序集、.NET 程序集、 架构、 映射、 绑定、 证书和等的项。 开发人员通过向其添加的所有其他项目或执行其他配置来完成应用程序。 开发人员，然后从.msi 文件安装应用程序、 测试以验证功能、 修复任何问题，然后导出该应用程序从[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]到.msi 文件。  
  
2. **测试。** 测试人员到.msi 文件导入[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]中的应用程序将创建测试计算机上运行[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 测试人员还从.msi 文件在主机计算机上安装应用程序。 测试人员测试和 bug 修复完成后，将从应用程序导出[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]到.msi 文件。  
  
3. **过渡环境。** IT 管理员将.msi 文件导入[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]过渡服务器上运行进行生产环境配置、 主机计算机上安装、 验证其功能，然后将完成的应用程序导出到.msi 文件。  
  
4. **生产环境。** IT 管理员将.msi 文件导入[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]在生产环境中，运行在主机计算机上安装该应用程序，然后启动该应用程序。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [BizTalk 应用程序部署的开发任务](../core/development-tasks-for-biztalk-application-deployment.md)  
  
-   [BizTalk 应用程序部署的测试任务](../core/testing-tasks-for-biztalk-application-deployment.md)  
  
-   [BizTalk 应用程序部署的暂存任务](../core/staging-tasks-for-biztalk-application-deployment.md)  
  
-   [BizTalk 应用程序部署的生产任务](../core/production-tasks-for-biztalk-application-deployment.md)