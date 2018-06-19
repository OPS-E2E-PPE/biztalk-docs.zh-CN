---
title: RosettaNet Pip |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- PIPs, clusters
- RosettaNet, PIPs
- PIPs, PIP specifications
- PIPs, segments
- PIPs, RosettaNet
- DTDs, DTD files
ms.assetid: 2f7e8db3-9ccb-403a-9fe7-58fbba3c4cb1
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1980f7c5e22259dc6c09d4f2d8dba31f3ac04d61
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22210789"
---
# <a name="rosettanet-pips"></a>RosettaNet Pip
RosettaNet 组织创建并维护合作伙伴接口流程 (PIP)，以便为所有 RosettaNet 消息交换提供通用的业务流程定义。  
  
 每个 PIP 规范都提供了文档类型定义 (DTD) 文件和消息指南文档。 DTD 文件定义了服务内容消息的结构。 消息指南文档作为可读的 HTML 文件，指定了元素级的约束， 同时，还提供了业务流程的完整定义。  
  
 PIP 规范的相关的详细信息，请参阅位于的 RosettaNet 网站[http://go.microsoft.com/FWLink/?LinkID=33859](http://go.microsoft.com/FWLink/?LinkID=33859)。  
  
## <a name="pip-contents"></a>PIP 内容  
 PIP 规范的作用如下：  
  
-   说明实施哪种公用流程模式  
  
-   说明如何配置公用流程  
  
-   提供对 PIP 内进行交换的文档的引用  
  
 PIP 规范包括三个主要部分： 业务操作视图 (BOV)、 功能服务视图 (FSV) 和实现 Framework 视图 (IFV)。 每个视图都指定了元素级的约束：  
  
-   BOV 指定了业务数据实体和业务流程的语义； 说明了开始状态、结束状态、合作伙伴角色， 还说明了角色之间的交互，并详细介绍了安全、审核和流程控制； 此外，还指定了业务文档和业务数据实体。  
  
-   FSV 指定了网络组件服务、代理和交互； 提供了运行 PIP 所需的网络组件设计，并说明了可能的网络组件交互。  
  
-   IFV 指定了运行 PIP 所需的网络协议消息格式和通信要求。  
  
## <a name="clusters-and-segments"></a>群集和段  
 按高级业务功能（群集）和子功能（段）对 PIP 进行分类。 群集和段将业务消息组织成可识别的类别。 下表列出了这些群集和段。  
  
|Clusters|段|  
|--------------|--------------|  
|0: RosettaNet 支持|0A： 管理<br /><br /> 0 C： 测试|  
|1： 合作伙伴的产品和服务复查|1A： 合作伙伴评审<br /><br /> 1B： 产品和服务复查|  
|2： 产品信息|2A： 准备分发<br /><br /> 2B： 产品更改通知<br /><br /> 2c： 产品设计信息<br /><br /> 二维： 协作设计和工程部门|  
|3： 订单管理|3A: Quote 和订单输入<br /><br /> 3B： 运输和分销<br /><br /> 3c： 返回和金融<br /><br /> 三维： 产品配置|  
|4： 库存管理|4A： 协作预测<br /><br /> 4B： 清单分配<br /><br /> 4c： 清单报表<br /><br /> 4 D： 库存补货<br /><br /> 4E： 销售报表<br /><br /> 4F： 价格保护|  
|5： 营销信息管理|5A： 潜在客户机会管理<br /><br /> 5B： 市场营销活动管理|  
|6： 服务和支持|6A： 提供和管理担保，服务包、 和协定服务<br /><br /> 6B： 提供和管理资产管理 （与 6A 合并）<br /><br /> 6 C： 请与技术支持和服务管理|  
|7： 制造|7A： 设计传输<br /><br /> 7B： 管理生产 WO 和 WIP<br /><br /> 7 C： 分发制造信息|  
  
 每个段均包括许多特定的消息 PIP。 例如，3A4 PIP 是订单管理群集（群集 3）和报价与订单录入段（群集 3 的段 A）的一部分。 本段包括其他相关的消息 PIP，如下所示：  
  
 群集 3： 订单管理  
  
-   段答： Quote 和订单输入  
  
    -   PIP 3A1： 请求引号  
  
    -   PIP 3A2： 请求价格和可用性  
  
    -   PIP 3A3： 请求购物车传输  
  
    -   PIP 3A4： 管理采购订单  
  
    -   PIP 3A5： 查询订单状态  
  
    -   PIP 3A6： 分发订单状态  
  
    -   …  
  
## <a name="see-also"></a>另请参阅  
 [RosettaNet 和 CIDX 标准消息传送](../../adapters-and-accelerators/accelerator-rosettanet/rosettanet-and-cidx-messaging-standards.md)   
 [RNIF 标准](../../adapters-and-accelerators/accelerator-rosettanet/rnif-standard.md)