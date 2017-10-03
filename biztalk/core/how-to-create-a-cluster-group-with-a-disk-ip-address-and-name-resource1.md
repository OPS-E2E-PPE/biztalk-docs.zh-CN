---
title: "如何使用磁盘，IP 地址，创建群集组，并命名 Resource1 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b361f721-60db-485e-9ce3-48a6871ebd79
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 63310706742ffcc10de5266dda7053da79fc04fe
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-create-a-cluster-group-with-a-disk-ip-address-and-name-resource"></a>如何创建具有磁盘、IP 地址和名称资源的群集组
为群集[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]组件和依赖项以通过 NetBIOS，群集通过网络来访问它**网络名称**必须在相同的群集组中创建资源。 对于群集的网络名称资源，可通过 TCP/IP 协议， **IP 地址**必须在相同的群集组中创建资源。 某些[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]依赖关系还需要使用聚集**物理磁盘**资源才能正常工作。 若要创建的群集组**物理磁盘**， **IP 地址**和**网络名称**资源，请按照下列步骤：  
  
### <a name="to-create-a-service-or-application-with-a-physical-disk-ip-address-and-network-name-resource"></a>创建具有物理磁盘、IP 地址和网络名称资源的服务或应用程序  
  
1.  在 Windows 中，单击**启动**，**程序**，**管理工具**，，然后**故障转移群集管理**启动故障转移群集管理程序。  
  
2.  将所有服务和应用程序故障转移到运行故障转移群集管理的群集节点上。 若要故障转移服务或应用程序，右键单击该服务或应用程序的左窗格中的故障转移群集管理、 指向**将此服务或应用程序到另一个节点移动**和单击此项可选择的目标节点。  
  
    > [!NOTE]
    >  承载正在运行的群集资源的群集节点是也称为**active**节点。 承载非运行群集资源的群集节点是也称为**被动**节点。  
  
3.  在左侧窗格中，右键单击**服务和应用程序**，单击**配置服务或应用程序**以启动高可用性向导，然后单击**下一步**.  
  
4.  单击以选择**文件服务器**单击**下一步**。  
  
    > [!NOTE]
    >  选择**文件服务器**此时都将作为与磁盘资源创建的群集组的简单方法。  
  
5.  上**客户端访问点**的高可用性向导页上，输入唯一的网络名称**名称**框中，例如*BizTalkCluster*，输入一个可用的 IP在地址**地址**，然后单击**下一步**。  
  
6.  上**选择存储**页上，单击此项可选择可用磁盘资源，然后单击**下一步**。  
  
7.  上**确认**页上，单击**下一步**若要创建的群集组。  
  
8.  上**摘要**页上，单击**完成**。