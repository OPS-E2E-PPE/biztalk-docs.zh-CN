---
title: BizTalk 组 |Microsoft Docs
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
ms.openlocfilehash: 960f7afa1138e1be3293ae3bc0c65898539630d8
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65528303"
---
# <a name="biztalk-groups"></a>BizTalk 组

## <a name="overview"></a>概述
*BizTalk 组*是一种通常表示企业、 部门、 中心或其他业务部门的需要包含的 BizTalk Server 实现的组织单位。 BizTalk 组拥有与 BizTalk Server 管理数据库的一对一关系 (称为 BizTalk Server 配置数据库中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)])。  
  
> [!NOTE]
>  虽然[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]组可能包含多个[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]计算机时，任何给定[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]计算机都只能与一个相关联[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]组。  
  
 BizTalk 管理数据库存储 BizTalk 组的配置信息和[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]该组中的计算机。 此配置信息指定为服务器和将以物理方式运行此逻辑的消息处理逻辑的一部分。 有关 BizTalk Server 管理数据库的详细信息，请参阅[BizTalk Server 中的数据库](../core/databases-in-biztalk-server.md)。  
  
 必须指定组中每个服务器安装相同的 BizTalk Server 管理数据库，以便可以管理从管理控制台的每个服务器。  
  
## <a name="see-also"></a>请参阅  
 [配置 BizTalk Server](../install-and-config-guides/configure-biztalk-server.md)   
 [管理组](../core/managing-groups.md)   
 [实体](../core/entities.md)