---
title: 第 4 课： 构建和部署程序集 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- building assemblies
- deploying, assemblies
- assemblies, building
- assemblies, deploying
ms.assetid: 58397c35-6048-4ac9-a8b8-a528dd1cb82a
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3ca5a539fdaea9026a7c18cae6f076e72df9efe2
ms.sourcegitcommit: 3fd1c85d9dc2ce7b77da75a5c2087cc48cfcbe50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2018
ms.locfileid: "25961923"
---
# <a name="lesson-4-building-and-deploying-the-assembly"></a>第 4 课： 构建和部署程序集
在本课程中，你可以生成和部署此项目以生成该程序集包含你在前面的课程中创建的架构。 此任务可确保到目前为止创建的工作中没有任何编译错误。  
  
 部署程序集将程序集的副本放在配置数据库，而将其安装在全局程序集缓存 (GAC)。 在下面的过程中，你部署直接从解决方案资源管理器。  
  
 当项目编译为程序集 （DLL 文件）、 [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]将保存在 DLL \<*驱动器*\>: \Program Files\\ [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk Accelerator for在项目文件夹内的 SWIFT\bin\Development 文件夹。  
  
### <a name="to-build-and-deploy-the-project"></a>生成并部署项目  
  
1.  在解决方案资源管理器，右键单击**SWIFTSchemas**，然后单击**生成**。  
  
    > [!NOTE]
    >  验证**生成成功**将显示在屏幕左下角。 在编译过程中，你可能会看到某些状态消息。 当处理 SWIFT 架构时，这些消息是正常的。 如果出现任何错误，请单击工具，然后单击 BizTalk Server 管理来打开 BizTalk Server 管理控制台。 使用 BizTalk 管理控制台中事件查看器的运行状况和活动跟踪 (HAT) 功能，若要更正你的错误并重新生成。  
  
2.  使用[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]资源管理器，浏览到 **\<*驱动器*\>: \labs\SWIFTProject\SWIFTSchemas\bin\Development**文件夹，并确认**SWIFTSchemas.dll**文件是否存在于此文件夹。  
  
3.  在解决方案资源管理器，右键单击**SWIFTSchemas**，然后单击**部署**。  
  
    > [!NOTE]
    >  验证**部署已成功**将显示在屏幕左下角。  
  
### <a name="to-confirm-deployment-success"></a>若要确认部署成功  
  
1.  单击**视图**，然后单击**BizTalk 资源管理器**。  
  
2.  展开**程序集**节点，并确认**SWIFTSchemas (1.0.0.0)** 出现在列表中。  
  
     如果 SWIFTSchemas 出现在列表中，程序集成功部署并可以引用和使用从其他[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]项目。  
  
 继续执行[模块 3： 添加的管道项目](../../adapters-and-accelerators/accelerator-swift/module-3-adding-a-pipeline-project.md)。