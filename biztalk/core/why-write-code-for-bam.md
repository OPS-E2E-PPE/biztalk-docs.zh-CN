---
title: "为什么为 BAM 编写代码？ | Microsoft Docs"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4434f50a-e0a9-45e0-8c68-a059011e1296
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 10b8ccb29d95daf8ccdf80d67faef3e50495af04
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="why-write-code-for-bam"></a>为什么为 BAM 编写代码？
在大多数情况下，您不必编写自己的代码就可以使用 BAM 工具执行跟踪功能。 这些工具是用于 Excel、BAM 管理实用程序和跟踪配置文件编辑器 (TPE) 的 BAM 外接程序。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中的 BAM 为 BizTalk 业务流程和消息传送组件（管道和端口）提供侦听器。 侦听器是一种用于装备应用程序的软件，以便应用程序可以基于配置文件以常规方式收集数据。 您可以使用跟踪配置文件编辑器来装备您的应用程序，以便使用这些侦听器。 有关跟踪配置文件编辑器中的详细信息，请参阅[跟踪配置文件编辑器](../core/tracking-profile-editor.md)。  
  
 有时，使用 BAM API 装备您的应用程序可能更有利，这主要体现在以下两种情况上：  
  
-   对于您要监视的主机，不存在 BAM 侦听器。  
  
-   内置的侦听器不支持复杂的应用程序。  
  
 如果没有任何内置拦截器，你可以使用 BAM **EventStream** Api 来捕获感兴趣的事件。  
  
> [!NOTE]
>  你可以组合**EventStream**类与**BAMInterceptor**类，以创建你自己的侦听器。 BAM API SDK 示例阐释了一个您可以扩展的简单的一般侦听器。 通过构建您自己的侦听器，您不必为每个应用程序都编写新代码，即可装备多种类似进程。 若要查看 BAM API SDK 示例，请参阅[BAM API （BizTalk Server 示例）](../core/bam-api-biztalk-server-sample.md)。  
  
## <a name="see-also"></a>另请参阅  
 [实现 BAM 解决方案](../core/implementing-bam-solutions.md)