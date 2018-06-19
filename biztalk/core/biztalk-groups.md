---
title: BizTalk 组 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Management database, groups
- groups
- groups, Management database
- groups, about groups
ms.assetid: 197cbcf6-c722-4cbb-9642-3cb8a34757e2
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5b9cd38012f0e2a7ba5f4cfcb56ae63678aacbf8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22231277"
---
# <a name="biztalk-groups"></a>BizTalk 组

## <a name="overview"></a>概述
*BizTalk 组*是通常表示企业、 部门、 中心或需要包含的 BizTalk Server 实现其他业务部门的组织的单元。 BizTalk 组具有一对一关系使用 BizTalk Server 管理数据库 (称为中的 BizTalk Server 配置数据库[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)])。  
  
> [!NOTE]
>  当 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 组可能包含多台 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 计算机时，任何给定的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 计算机都只能与单个 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 组相关联。  
  
 BizTalk 管理数据库存储 BizTalk 组及其所包含的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 计算机的配置信息。 此配置信息指定了服务器的消息处理逻辑的一部分，以及将运行此逻辑的物理位置。 有关 BizTalk Server 管理数据库的详细信息，请参阅[BizTalk Server 中的数据库](../core/databases-in-biztalk-server.md)。  
  
 必须为组中的每个服务器安装指定同一个 BizTalk Server 管理数据库，以便可以通过管理控制台管理每个服务器。  
  
## <a name="see-also"></a>另请参阅  
 [配置 BizTalk Server](../install-and-config-guides/configure-biztalk-server.md)   
 [管理组](../core/managing-groups.md)   
 [实体](../core/entities.md)