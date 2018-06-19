---
title: 第 8 课： 构建和部署程序集 |Microsoft 文档
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
ms.assetid: 74c9dfbd-8365-4600-8885-a9d9c3490dd5
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 607b3a304260e67a6640e579924705719ff8b850
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25960915"
---
# <a name="lesson-8-building-and-deploying-the-assembly"></a>第 8 课： 构建和部署程序集
在本课程中，你可以生成和部署管道项目生成包含你在前面的步骤中创建管道的程序集。 本课程可确保到目前为止创建的工作中没有任何编译错误。  
  
 将项目编译为程序集 (DLL) 文件并将其保存在\<*驱动器*\>: files\microsoft BizTalk Accelerator for SWIFT\bin\Development 文件夹。  
  
### <a name="to-build-and-deploy-the-project"></a>生成并部署项目  
  
1.  在解决方案资源管理器，右键单击**SWIFTPipelines**，然后单击**生成**。  
  
    > [!NOTE]
    >  在编译过程中，不应看到任何失败。 如果这样做，请检查错误的源，其更正，然后重新生成项目。 但是，可能会看到大量的 A4SWIFT 管道组件相关的警告。 您可以更正导致通过设置这些警告的条件**Copy Local**的管道组件引用的属性**False**。 有关详细信息，请参阅"生成管道项目可能会导致警告"[杂项已知问题](http://msdn.microsoft.com/library/bc94c781-2a56-4f80-8ecb-e654de2f6ed6)。  
  
2.  若要验证的 SWIFTPipelines.dll 创建文件，请使用[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]资源管理器，浏览到\<*驱动器*:\>\labs\SWIFTProject\SWIFTPipelines\bin\Development，并确保该文件中存在此文件夹中。  
  
3.  在解决方案资源管理器，右键单击**SWIFTPipelines**，然后单击**部署**。  
  
    > [!NOTE]
    >  在部署过程中，你不应看到任何失败或警告。 如果这样做，请检查错误的源、 其更正，然后重新部署该项目。  
  
4.  若要在符合部署成功，**视图**菜单[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]，单击**BizTalk 资源管理器**。  
  
5.  右键单击**BizTalk 配置数据库**，然后单击**刷新**。  
  
6.  展开**程序集**节点并确认快捷键成功部署**SWIFTPipelines (1.0.0.0)**。  
  
 继续执行[模块 4： 创建 XML 接收和平面文件发送端口](../../adapters-and-accelerators/accelerator-swift/module-4-adding-an-xml-receive-location-and-flat-file-send-port.md)。