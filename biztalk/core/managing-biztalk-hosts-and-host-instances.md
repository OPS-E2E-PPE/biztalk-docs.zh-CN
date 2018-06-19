---
title: 管理 BizTalk 主机和主机实例 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [hosts]
- hosts, managing
- managing [hosts], about managing hosts
ms.assetid: 7f329804-ca44-4799-8a5d-38b3146d8e5e
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0e60981f69bc3ff71bdd8581659f9cdd20f87467
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22262581"
---
# <a name="managing-biztalk-hosts-and-host-instances"></a>管理 BizTalk 主机和主机实例
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 主机是一个由零个或多个 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 运行时进程组成的逻辑集合，您可以在其中部署诸如适配器处理程序、接收位置（包括管道）和业务流程等项。 有关主机的详细信息，请参阅[主机](../core/hosts.md)。  
  
 主机实例是消息处理、接收和传输发生的过程。 运行每个服务器上安装一个主机实例[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]具有映射到该服务器的一个或多个主机。 有关主机实例的详细信息，请参阅[主机实例](../core/host-instances.md)。  
  
 主机具有以下特性：  
  
-   主机是 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 对象的逻辑容器。  
  
-   每个服务器上只能存在特定主机的一个实例。  
  
-   可以将一个主机映射到多个服务器。  
  
 主机实例具有以下特性：  
  
-   主机实例是 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 对象的物理容器。  
  
-   将服务器映射到主机时，即创建了一个主机实例。  
  
-   在进行负载平衡或故障转移时，一个服务器上可以存在不同主机的多个主机实例。  
  
 下图显示了服务器、主机和主机实例之间的关系：  
  
 ![主机、 主机实例和服务器关系](../core/media/ebiz-ops-adm01.gif "ebiz_ops_adm01")  
主机、 主机实例和服务器之间的关系  
  
## <a name="in-this-section"></a>本节内容  
  
-   [如何创建 BizTalk 服务器宿主环境](../core/how-to-create-a-biztalk-server-hosting-environment.md)  
  
-   [如何创建新的主机](../core/how-to-create-a-new-host.md)  
  
-   [如何修改主机属性](../core/how-to-modify-host-properties.md)  
  
-   [如何删除主机](../core/how-to-delete-a-host.md)  
  
-   [如何添加的主机实例](../core/how-to-add-a-host-instance.md)  
  
-   [如何启动的主机实例](../core/how-to-start-a-host-instance.md)  
  
-   [如何停止主机实例](../core/how-to-stop-a-host-instance.md)  
  
-   [如何删除主机实例](../core/how-to-delete-a-host-instance.md)  
  
-   [如何修改主机实例属性](../core/how-to-modify-host-instance-properties.md)