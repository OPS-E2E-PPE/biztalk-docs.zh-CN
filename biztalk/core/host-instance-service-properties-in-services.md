---
title: 主机实例服务中的服务属性 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8b317161-83a9-42d5-b24f-48ff1e54b94a
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bd58a240ec2be9c2b61cdb52d0c6461ffb99f5cd
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65344242"
---
# <a name="host-instance-service-properties-in-services"></a>在服务中的主机实例服务属性
## <a name="host-instance-service-properties-in-services"></a>在服务中的主机实例服务属性  
 创建 BizTalk 主机实例时，还创建中服务的服务。 下表讨论了最常见属性。  
  
|Option|Description|  
|------------|-----------------|  
|常规：**启动类型**|默认设置为**自动**以允许主机实例重新启动计算机时自动启动。 在生产环境中，此属性通常始终设置为**自动**。|  
|登录：**帐户**|配置了 BizTalk 或创建新的主机实例时，将指定设置为用户帐户。 当 BizTalk 和 SQL Server 位于不同计算机上时，帐户必须是域帐户。 如果 BizTalk 和 SQL Server 位于同一台计算机上，帐户可以是域帐户或本地帐户。|  
|恢复：**第一次失败**|默认设置为**重新启动服务**。 如果主机实例第一次意外停止，则此设置将尝试重新启动主机实例。<br /><br /> 如果主机实例成功启动后立即停止，则**失败的第二个**应用属性。<br /><br /> 如果主机实例无法启动，则**失败的第二个**属性将不适用。 会不进行任何其他的重新启动尝试。 主机实例将保持停止状态。|  
|恢复：**第二次失败**|默认设置为**重新启动服务**。 如果主机实例第二次意外停止，则此设置将尝试重新启动主机实例。<br /><br /> 如果主机实例成功启动后立即停止，则**后续失败**应用属性。<br /><br /> 如果主机实例无法启动，则**后续失败**属性将不适用。 会不进行任何其他的重新启动尝试。 主机实例将保持停止状态。|  
|恢复：**后续的失败**|默认设置为**重新启动服务**。 如果主机实例第三次意外停止，则此设置将尝试重新启动主机实例。<br /><br /> 如果主机实例成功启动后立即停止，则**后续失败**属性将继续应用。<br /><br /> 如果主机实例无法启动，则**后续失败**属性将不适用。 会不进行任何其他的重新启动尝试。 主机实例将保持停止状态。|  
|恢复：**之后重新启动服务**|默认值为 1 分钟，并且可以根据需要增大该值。|  
|依存关系|**所有**BizTalk 主机实例将开始之前，必须启动列出的组件。 这包括企业单一登录。 如果使用 Windows Server 2008，请参阅以下知识库文章：<br /><br /> [942284](http://support.microsoft.com/kb/942284) BizTalk Service 服务可能无法正常启动时重新启动正在运行 Windows Vista 或 Windows Server 2008 的计算机|  
  
 **请注意**服务中的 BizTalk 主机实例属性也存储在 HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\services\BTSSvc$*BizTalkHostName*注册表项。  
  
### <a name="recovery"></a>恢复  
 当主机实例服务启动失败时，在服务中的恢复功能不提供无限制的服务重新启动尝试。 通过修改恢复属性，就可以改进 BizTalk 主机实例的正常运行时间。 将导致停止的 BizTalk 主机实例的最常见方案包括：  
  
- 与 SQL Server 的网络连接中断  
  
- 内存不足异常  
  
- 访问冲突  
  
  **可能的方案**  
  
- SQL Server 意外关闭。 在此情况下，**第一次失败**属性将应用。 默认值**第一次失败**并**之后重新启动服务**1 分钟之后进行设置，次重新启动尝试。 如果 SQL Server 在 1 分钟后仍不可用，将不进行任何其他的重新启动尝试。 主机实例将保持停止状态。  
  
- SQL Server 已群集化且发生故障转移。 在故障转移多个在 5 分钟。 在此方案中，默认值**第一次失败**并**之后重新启动服务**设置将尝试之后 1 分钟一次重新启动。 在重新启动将失败，因为 SQL Server 是仍处于脱机状态。 因此，将不进行任何其他的重新启动尝试。 主机实例将保持停止状态。  
  
  **建议**  
  
- 当停止 SQL Server 或故障转移 SQL 群集，手动停止 BizTalk 主机实例。 SQL Server 联机后，重新启动主机实例。  
  
- 如果它是一种常见情况的 SQL 群集故障转移时间长于 1 分钟时间，提高**之后重新启动服务**值，使 SQL 群集处于联机状态。  
  
- 在 SQL Server 维护由非 BizTalk 管理员，请考虑提高**之后重新启动服务**值。 非 BizTalk 管理员可能会停止/启动 SQL Server 却没有意识到 biztalk 的影响。  
  
## <a name="see-also"></a>请参阅  
 [管理 BizTalk 主机和主机实例](../core/managing-biztalk-hosts-and-host-instances.md)