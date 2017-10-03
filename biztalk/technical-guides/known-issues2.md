---
title: "已知问题 2 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 709c19ea-1138-49f8-8898-c2d2c60c3923
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 28378697c145f48881f4ae850488c0c5afcb4ea3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="known-issues"></a>已知问题
下表列出了所有已知的问题[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]用于 Operations Manager 2007 R2/2012年管理包。  
  
|问题|Description|解决方法|  
|-----------|-----------------|----------------|  
|性能计数器重启后相关错误和警告|你可能会看到性能逆时针相关的错误和警告 Operations Manager 事件日志中的代理后重新启动。|管理包在出现错误后将恢复并重新运行。|  
|对象发现相关 Operations Manager 事件日志中的警告|时 （包括关系发现） 发现未能找到实例，则会将警告写入 Operations Manager 事件日志中指出该 null 返回了发现脚本。||  
|警报在群集环境中的物理节点是不可靠|有两个群集环境中的监视与关联的已知的问题：<br /><br /> -当从 active 到被动节点更改，节点和关联的项目的监视状态可能不会反映正确操作控制台中。<br />-在群集环境中，Operations Manager 创建一个虚拟节点可能重复的状态和警报来显示它们。|在群集环境中包含主动/被动节点;依赖于虚拟节点中显示的监视信息。 这是因为虚拟节点始终指向时间处于活动状态的任何时刻的物理节点。|  
|关系和依赖关系监视器|以下是与关系和依赖关系监视器相关的已知的问题： 发生这种情况主要 BizTalk 管理包时指定 SCOM 服务器上重新导入。 用户然后需要，请参阅注释与给定的相同"重现此问题的步骤"部分中的前一状态。<br /><br /> -不会发现 BizTalk 项目之间的关系。<br />依赖项关系不会显示按预期方式。<br />-汇总的监视状态不会发生。<br />的即使在关系发现之后未初始化某些依赖关系监视器。|若要解决这些问题的解决方法如下所示：<br /><br /> <ul><li>重新启动 BizTalk 代理计算机上的 Operations Manager 运行状况服务。 <br />     -或者-</li><li>运行刷新运行状况服务状态和缓存任务。 若要执行此操作的步骤如下所示：<br /><br /> <ol><li>在导航树中，选择 Operations Manager 代理代理运行状况状态。</li><li>选择在代理状态下运行 BizTalk Server 运行状况服务观察程序的计算机。</li><li>选择在代理状态下的代理状态。</li><li>单击右侧面板中的刷新运行状况服务状态和缓存任务。</li><li>在运行任务-刷新运行状况服务状态和缓存对话框中，单击运行。</li></ol></li></ul>|  
|显示错误状态发送端口和接收位置|SSO 服务已关闭，BizTalk Server 管理包不会不显示发送端口的正确状态和接收位置。||