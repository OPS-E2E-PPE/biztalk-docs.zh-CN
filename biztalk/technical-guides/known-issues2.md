---
title: 已知问题 2 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 709c19ea-1138-49f8-8898-c2d2c60c3923
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9d9988ff11bb8380d4f5d7d40a1eab7a6ebfdb69
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396299"
---
# <a name="known-issues"></a>已知问题
下表列出了所有已知的问题[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]适用于 Operations Manager 2007 R2/2012年管理包。  
  
|问题|Description|解决方法|  
|-----------|-----------------|----------------|  
|性能计数器后重新启动相关错误和警告|您可能会看到性能计数器相关的错误和警告 Operations Manager 事件日志中的代理后重新启动。|管理包出现错误后恢复并重新运行。|  
|对象发现相关 Operations Manager 事件日志中的警告|时未能找到实例 （包括关系发现） 的发现，表明该 null 返回的发现脚本在 Operations Manager 事件日志中写入警告。||  
|警报在群集环境中的物理节点中是不可靠|有两个群集环境中的监视与关联的已知的问题：<br /><br /> -当从活动到被动节点更改，监视状态的节点和关联的项目可能不能正确反映在操作控制台中。<br />-在群集环境中，Operations Manager 创建的虚拟节点可能会显示重复的状态和警报。|在群集环境中，其中包含主动/被动节点;依赖于虚拟节点中显示的监视信息。 这是因为虚拟节点始终指向在处于活动状态的任何点及时的物理节点。|  
|关系和依赖关系监视器|以下是与关系和依赖关系监视器相关的已知的问题：主要是在给定的 SCOM 服务器上重新导入 BizTalk 管理包时，将发生这种情况。 然后要求用户，请参阅注释与给定的相同"重现此问题的步骤"部分中的前一状态。<br /><br /> 的未发现 BizTalk 项目之间关系。<br />-依赖关系未按预期显示。<br />-汇总的监视状态不会发生。<br />的即使关系发现某些依赖关系监视器均未初始化。|若要解决这些问题的解决方法如下所示：<br /><br /> <ul><li>重新启动 BizTalk 代理计算机上的 Operations Manager 运行状况服务。 <br />     -或-</li><li>运行刷新运行状况服务状态和缓存任务。 若要执行此操作的步骤如下所示：<br /><br /> <ol><li>在导航树中，选择 Operations Manager 代理程序代理运行状况状态。</li><li>选择在代理状态下运行 BizTalk Server 运行状况服务观察程序中的计算机。</li><li>选择在代理状态下的代理状态。</li><li>单击右侧面板中的刷新运行状况服务状态和缓存任务。</li><li>在运行任务-刷新运行状况服务状态和缓存对话框中单击运行。</li></ol></li></ul>|  
|显示错误状态的发送端口和接收位置|SSO 服务已关闭，BizTalk Server 管理包不会不显示正确状态的发送端口和接收位置。||