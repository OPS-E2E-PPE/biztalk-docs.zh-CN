---
title: 管理 BizTalk 程序集 |Microsoft Docs
description: 若要使用在 BizTalk Server 中，包括添加、 更新、 查看依赖项，以及删除程序集的程序集的链接
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 62cc92f5-a1ea-46e4-88e6-b8a71a0c40a2
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9a5657484f45c7426b8f51e8ef1258c2d0d62a4d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65328766"
---
# <a name="manage-biztalk-assemblies"></a>管理 BizTalk 程序集

## <a name="overview"></a>概述
本部分说明了使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台或 BTSTask 命令行工具来部署到 BizTalk 组后管理 BizTalk 程序集。 BizTalk 程序集是包含资源信息，如业务流程、 管道、 架构和映射中使用的 Microsoft Windows DLL 文件[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]业务解决方案。 BizTalk 程序集的背景信息，请参阅[BizTalk 程序集](../core/biztalk-assemblies.md)。  
  
> [!IMPORTANT]
>  部署或取消部署属性架构可能暴露敏感数据，并随后暴露在跟踪的敏感信息。 每当部署或已取消部署包含属性架构的程序集时，事件查看器记录的事件在 Windows 应用程序事件日志中。 应检查这些消息，以确保所有程序集部署活动均符合你的策略的任何敏感数据在事件日志。 (部署为事件日志中生成的消息："用户"{1}"已部署程序集"{0}"包含属性架构"。 取消部署事件日志中生成的消息为："用户"{1}"已取消部署程序集"{0}"包含属性架构"。)  
> 
> [!NOTE]
>  Microsoft Windows Management Instrumentation (WMI) 对象模型可用于创建和运行自动执行管理任务的脚本。 有关使用 WMI 的信息，请参阅**WMI 类引用** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。
  
 开发人员可使用[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]开发 BizTalk 程序集，如中所述[开发 BizTalk Server 应用程序](../core/developing-biztalk-server-applications.md)，并可以将其从部署[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]到[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]中所述[部署从 Visual Studio 到 BizTalk 应用程序的 BizTalk 程序集](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)。 开发人员还可以管理 BizTalk 程序集在开发过程中通过使用管理控制台中，在本部分中所述。  
  
## <a name="next-steps"></a>后续步骤 
  
-   [向应用程序中添加 BizTalk 程序集](../core/how-to-add-a-biztalk-assembly-to-an-application.md)  
  
-   [修改 BizTalk 程序集的部署选项](../core/how-to-modify-the-deployment-options-of-a-biztalk-assembly.md)  
  
-   [查看 BizTalk 程序集的依赖关系](../core/how-to-view-the-dependencies-for-a-biztalk-assembly.md)  
  
-   [从应用程序中删除 BizTalk 程序集](../core/how-to-remove-a-biztalk-assembly-from-an-application.md)