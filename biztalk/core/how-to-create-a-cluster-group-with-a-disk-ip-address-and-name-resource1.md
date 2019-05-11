---
title: 如何创建具有磁盘、 IP 地址的群集组并将命名 Resource1 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b361f721-60db-485e-9ce3-48a6871ebd79
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 60b76da3fe031881eea3491469ac0f9d0bfe5c48
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385597"
---
# <a name="how-to-create-a-cluster-group-with-a-disk-ip-address-and-name-resource"></a>如何创建具有磁盘、 IP 地址和名称资源的群集组
对于聚集[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]组件和依赖项通过 NetBIOS，群集网络上可以访问**网络名称**必须在同一群集组中创建资源。 为群集的网络名称资源，可通过 TCP/IP 协议**IP 地址**必须在相同的群集组中创建资源。 某些[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]依存关系还需要使用群集**物理磁盘**资源才能正常工作。 若要创建的群集组与**物理磁盘**， **IP 地址**并**网络名称**资源，请执行以下步骤：  
  
### <a name="to-create-a-service-or-application-with-a-physical-disk-ip-address-and-network-name-resource"></a>若要创建具有物理磁盘、 IP 地址和网络名称资源的服务或应用程序  
  
1.  在 Windows 中，单击**启动**，**程序**，**管理工具**，然后**故障转移群集管理**开始故障转移群集管理程序。  
  
2.  故障转移所有服务和群集节点上运行故障转移群集管理的应用程序。 若要故障转移服务或应用程序，右键单击服务或在左窗格中的故障转移群集管理的应用程序，指向**将此服务或应用程序到另一个节点移动**并单击以选择目标节点。  
  
    > [!NOTE]
    >  承载正在运行的群集资源的群集节点是也称为**active**节点。 承载非正在运行群集资源的群集节点是也称为**被动**节点。  
  
3.  在左侧窗格中，右键单击**服务和应用程序**，单击**配置服务或应用程序**以启动高可用性向导，然后单击**下一步**.  
  
4.  单击此项可选择**文件服务器**然后单击**下一步**。  
  
    > [!NOTE]
    >  选择**文件服务器**此时完成了简单方法以创建具有磁盘资源的群集组作为。  
  
5.  上**客户端访问点**高可用性向导的页上，输入一个唯一的网络名称**名称**框中，例如*BizTalkCluster*，输入一个可用 IP在解决**地址**，然后单击**下一步**。  
  
6.  上**选择存储**页上，单击此项可选择可用磁盘资源，然后单击**下一步**。  
  
7.  上**确认**页上，单击**下一步**若要创建的群集组。  
  
8.  上**摘要**页上，单击**完成**。