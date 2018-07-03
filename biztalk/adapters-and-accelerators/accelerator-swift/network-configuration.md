---
title: 网络配置 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- deploying, network configuration
ms.assetid: fb6265b8-2e6d-4344-bb44-4f4fd995382d
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8fb693b9718b7c92e24f3537bea7ef27267f9a05
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36967438"
---
# <a name="network-configuration"></a>网络配置
本部分提供在部署中配置网络的规范性指南。 有关详细信息，请参阅[为部署做好准备](../../adapters-and-accelerators/accelerator-swift/preparing-for-deployment.md)。  

 您交换机中定义虚拟局域网 (Vlan)，然后连接适当的电缆。 通过定义 Vlan，指定为每个网络段或层交换机上的端口。 必须为每个以下环境创建 VLAN:  

- [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] 接收和发送层  

- [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] 业务流程和数据库层  

- 企业网络  

  定义 Vlan 之后，可以到交换机上的相应端口从服务器连接的网络电缆。  

  本部分包含：  

- [物理关系图](../../adapters-and-accelerators/accelerator-swift/physical-diagram.md)  

- [网络负载均衡](../../adapters-and-accelerators/accelerator-swift/network-load-balancing.md)
