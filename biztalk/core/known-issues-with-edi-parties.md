---
title: 已知问题 EDI 方 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 86475960-cdb2-4b39-817a-b5d834f498a9
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fddda6dd62e8e3bd2d38574343b7fcb0e0d76f89
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22261781"
---
# <a name="known-issues-with-edi-parties"></a>EDI 参与方的已知问题
本部分包含的主题将介绍 EDI 参与方和合作伙伴协议管理器的已知问题。  
  
## <a name="a-cache-refresh-period-delays-availability-of-a-changed-party-property"></a>缓存刷新周期会延迟已更改参与方属性的可用性  
 如果在 PAM 中更改参与方或全局属性，在缓存刷新（每十五分钟刷新一次）或重新启动 BizTalk 服务之后该属性才可用于 BizTalk 运行时。  
  
## <a name="see-also"></a>另请参阅  
 [配置 EDI 确认](../core/configuring-edi-acknowledgments.md)   
 [协议在 EDI 处理过程中的角色](../core/the-role-of-agreements-in-edi-processing.md)   
 [配置 EDI 属性](../core/configuring-edi-properties.md)   
 [配置全局或后备协议属性](../core/configuring-global-or-fallback-agreement-properties.md)