---
title: 物理关系图 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- deploying, network configuration
ms.assetid: 4291727b-8687-496a-8f03-0da4b3201967
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 695c8ca0fd03fd8324f5b0ab86d72c1c0b6daf9f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36978630"
---
# <a name="physical-diagram"></a>物理关系图
一个典型的部署具有聚集 BizTalk Server 计算机的消息 （发送和接收），用于执行业务流程 （业务流程），用于访问 InfoPath 模板 （MRSR 站点） 的 BizTalk Server 计算机的 BizTalk Server 计算机和群集的 SQL Server 计算机。 下面的部署可确保从 intranet 和 Internet 用户的安全环境。  
  
> [!NOTE]
>  此典型的部署是推荐的配置。 你将需要验证你自己的业务需求和服务器配置，以确定你的部署可正常工作。  
  
 可以扩展此部署向上或向下扩展或，具体取决于使用情况配置文件和不断增长的业务需求。 典型的可伸缩性方案包括在每个群集，以确保更高的可用性或更高的吞吐量中添加一个或多个服务器。 较小的企业可能倾向于缩减回其部署具有相同的服务器执行多个函数，如具有一个[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]计算机处理业务流程和消息传送。 Microsoft[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]支持在一台服务器上部署。 下图显示了完整的 A4SWIFT 部署的建议的分布式的部署环境的示例。  
  
 ![](../../adapters-and-accelerators/accelerator-swift/media/fsa-deploy-full.gif "FSA_Deploy_Full")  
完整的 A4SWIFT 部署示例