---
title: "网络配置 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: deploying, network configuration
ms.assetid: fb6265b8-2e6d-4344-bb44-4f4fd995382d
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 83a9e8ffe6b278c91429835c3ae32c96d45ef22e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="network-configuration"></a>网络配置
本部分提供在你的部署中配置网络的规范性指引。 有关详细信息，请参阅[为部署做好准备](../../adapters-and-accelerators/accelerator-swift/preparing-for-deployment.md)。  
  
 你定义在交换机中的虚拟局域网 (Vlan)，然后连接适当的电缆。 通过定义 Vlan，指定为每个网络段或层交换机上的端口。 为每个以下的环境，必须创建 VLAN:  
  
-   [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]接收和发送层  
  
-   [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]业务流程和数据库层  
  
-   企业网络  
  
 定义 Vlan 后，你可以连接的网络电缆从服务器到交换机上的相应端口。  
  
 本部分包含：  
  
-   [物理关系图](../../adapters-and-accelerators/accelerator-swift/physical-diagram.md)  
  
-   [网络负载平衡](../../adapters-and-accelerators/accelerator-swift/network-load-balancing.md)