---
title: "开发 EDI 架构 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7a8fbf3d-ebc7-47f6-87fa-e45722651262
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b241b5d0477d7aa477511c43b642e4e312f2651a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="developing-edi-schemas"></a>开发 EDI 架构
本部分中的主题介绍如何修改 EDI 架构以用于 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。  
  
 若要在解决方案中使用文档架构，你需要通过将其添加到中的 BizTalk 项目部署架构[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，然后生成并部署项目。 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]将部署中默认 BizTalk 应用程序 1 的项目。 你可以看到通过打开部署的架构**架构**节点下的**BizTalk 应用程序 1**节点**应用程序**中的节点[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。 通过使用命令行部署工具 `BTSTask`，可将程序集部署到不同的应用程序中。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 配置向导会自动部署服务和控制架构。 若要查看它们，请单击**架构**中的节点**BizTalk EDI 应用程序**在管理控制台中的节点。 有关这些架构的详细信息，请参阅[EDI 服务和控制架构](../core/edi-service-and-control-schemas.md)。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [修改 EDI 架构](../core/modifying-edi-schemas.md)  
  
-   [信封架构中的自定义枚举](../core/customizing-enumerations-in-the-envelope-schema.md)  
  
-   [配置跨字段验证](../core/configuring-cross-field-validation.md)  
  
## <a name="see-also"></a>另请参阅  
 [开发和配置 BizTalk Server EDI 解决方案](../core/developing-and-configuring-biztalk-server-edi-solutions.md)