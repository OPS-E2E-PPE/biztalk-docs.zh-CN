---
title: 为什么为 BAM 编写代码？ | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4434f50a-e0a9-45e0-8c68-a059011e1296
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 48d8d6fb370ca7815cf0df2d3685d73c60bc8d84
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65242805"
---
# <a name="why-write-code-for-bam"></a>为什么为 BAM 编写代码？
在大多数情况下您可以使用 BAM 工具而无需编写自己的代码来执行跟踪功能。 这些工具是 BAM 外接程序 Excel、 BAM 管理实用程序，和跟踪配置文件编辑器 (TPE)。 中的 BAM[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]为 BizTalk 业务流程和消息传送组件 （管道和端口） 提供侦听器。 侦听器是检测应用程序，以便它可以基于配置文件以一般方式收集数据的软件。 您还可以检测应用程序以使用跟踪配置文件编辑器中使用这些侦听器。 有关跟踪配置文件编辑器的详细信息，请参阅[跟踪配置文件编辑器](../core/tracking-profile-editor.md)。  
  
 有两种主要方案，但是，在其中你会发现更有利检测使用 BAM Api 的应用程序：  
  
- 不存在 BAM 侦听器你想要监视的主机。  
  
- 内置的侦听器不允许你的应用程序的复杂性。  
  
  当有内置的侦听器时，可以使用 BAM **EventStream** Api，以捕获感兴趣的事件。  
  
> [!NOTE]
>  你可以组合**EventStream**类与**BAMInterceptor**类，以创建您自己的侦听器。 BAM API SDK 示例说明了简单的一般侦听器，您可以充分利用。 通过构建您自己的侦听器可以检测多种类似进程，而无需为每个应用程序编写新代码。 若要查看 BAM API SDK 示例，请参阅[BAM API （BizTalk Server 示例）](../core/bam-api-biztalk-server-sample.md)。  
  
## <a name="see-also"></a>请参阅  
 [实现 BAM 解决方案](../core/implementing-bam-solutions.md)