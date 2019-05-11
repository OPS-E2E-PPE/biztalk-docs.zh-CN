---
title: 管理 BizTalk 主机和主机实例 |Microsoft Docs
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
ms.openlocfilehash: 5ac3edd7b2aa87463e28a60810cf85a87444a88f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65380614"
---
# <a name="managing-biztalk-hosts-and-host-instances"></a>管理 BizTalk 主机和主机实例
一个[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]主机是一组逻辑的零个或多[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]运行时进程在其中部署诸如适配器处理程序、 接收位置 （包括管道） 和业务流程。 有关主机的详细信息，请参阅[主机](../core/hosts.md)。  
  
 主机实例是消息处理、 接收和传输发生的过程。 运行每个服务器上安装主机实例[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]具有一个或多个主机映射到该服务器。 有关主机实例的详细信息，请参阅[主机实例](../core/host-instances.md)。  
  
 主机具有以下特征：  
  
- 主机是逻辑容器[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]对象。  
  
- 每个服务器上可以存在的特定主机的一个实例。  
  
- 可以将映射到多个服务器的一台主机。  
  
  主机实例具有以下特征：  
  
- 主机实例是物理容器[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]对象。  
  
- 将服务器映射到主机时创建的主机实例。  
  
- （不同的主机） 的多个实例可以存在的服务器上进行负载平衡或故障转移时。  
  
  下图显示了服务器、 主机和主机实例之间的关系。  
  
  ![主机、 主机实例和服务器之间的关系](../core/media/ebiz-ops-adm01.gif "ebiz_ops_adm01")  
  主机、 主机实例和服务器之间的关系  
  
## <a name="in-this-section"></a>本节内容  
  
-   [如何创建 BizTalk Server 宿主环境](../core/how-to-create-a-biztalk-server-hosting-environment.md)  
  
-   [如何创建新的主机](../core/how-to-create-a-new-host.md)  
  
-   [如何修改主机属性](../core/how-to-modify-host-properties.md)  
  
-   [如何删除主机](../core/how-to-delete-a-host.md)  
  
-   [如何添加主机实例](../core/how-to-add-a-host-instance.md)  
  
-   [如何启动主机实例](../core/how-to-start-a-host-instance.md)  
  
-   [如何停止主机实例](../core/how-to-stop-a-host-instance.md)  
  
-   [如何删除主机实例](../core/how-to-delete-a-host-instance.md)  
  
-   [如何修改主机实例属性](../core/how-to-modify-host-instance-properties.md)