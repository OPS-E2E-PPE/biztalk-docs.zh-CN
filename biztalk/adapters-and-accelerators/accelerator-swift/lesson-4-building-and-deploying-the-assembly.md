---
title: 第 4 课：生成和部署程序集 |Microsoft Docs
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
ms.openlocfilehash: d180180f178defe4fc4d93de36fb8ac8f6ed88a0
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530299"
---
# <a name="lesson-4-building-and-deploying-the-assembly"></a>第 4 课：生成和部署程序集
在本课程中，将生成和部署此项目以生成包含你在前面的课程中创建的架构的程序集。 此任务可确保到目前为止创建的工作中没有任何编译错误。  
  
 部署程序集的程序集的副本放在配置数据库，并将其安装在全局程序集缓存 (GAC) 中。 在下面的过程中，则直接从部署解决方案资源管理器。  
  
 当项目编译为程序集 （DLL 文件）、 Microsoft[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]将保存在 DLL \<*驱动器*\>: \Program Files\\Microsoft BizTalk Accelerator for SWIFT\bin\在项目文件夹内的开发文件夹。  
  
### <a name="to-build-and-deploy-the-project"></a>生成并部署项目  
  
1. 在解决方案资源管理器中右键单击**swift 架构**，然后单击**生成**。  
  
   > [!NOTE]
   >  确认**生成成功**显示在屏幕的左下角。 在编译过程中，可能会看到某些状态消息。 SWIFT 架构在处理时，这些消息是正常的。 如果出现任何错误，单击工具，然后单击以打开 BizTalk Server 管理控制台的 BizTalk Server 管理。 使用 BizTalk 管理控制台中的事件查看器和运行状况与活动跟踪 (HAT) 功能来更正错误并重新生成。  
  
2. 使用[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]资源管理器，浏览到 **\<*驱动器*\>: \labs\SWIFTProject\SWIFTSchemas\bin\Development**文件夹中，并确认**SWIFTSchemas.dll**文件是否存在于此文件夹。  
  
3. 在解决方案资源管理器中右键单击**swift 架构**，然后单击**部署**。  
  
   > [!NOTE]
   >  确认**部署已成功**显示在屏幕的左下角。  
  
### <a name="to-confirm-deployment-success"></a>若要确认部署成功  
  
1. 单击**视图**，然后单击**BizTalk 浏览器**。  
  
2. 展开**程序集**节点，并确认**swift 架构 (1.0.0.0)** 出现在列表中。  
  
    Swift 架构将显示在列表中，如果该程序集已成功部署并可以引用和使用从其他[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]项目。  
  
   请继续执行[模块 3:添加管道项目](../../adapters-and-accelerators/accelerator-swift/module-3-adding-a-pipeline-project.md)。