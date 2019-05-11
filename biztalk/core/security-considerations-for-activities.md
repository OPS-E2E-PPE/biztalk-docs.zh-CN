---
title: 有关活动的安全注意事项 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2fc49afd-a1c3-4ac7-8b89-11be667221e2
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e6c6faca1adf03c216cc0ce6fd4510c937cb1963
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65250994"
---
# <a name="security-considerations-for-activities"></a>有关活动的安全注意事项
侦听 WCF 适配器时，使用的安全角色都与用于其他 BAM 解决方案相同。 侦听 WCF 适配器的其他注意事项包括选择要使用的正确的用户和事件写入者角色。  
  
 使用 WCF 服务和 WCF 适配器时，所有与 BAM 相关的数据是由所选角色写入 BAM 主导入数据库中。  
  
 可以通过评估你的解决方案的方案选择适当的用户角色配置：  
  
- 如果解决方案需要很多新服务，由许多不同的活动跟踪，并将所有相同的用户帐户下运行，但最好使用 BAM_EVENT_WRITER 超级角色来写入侦听到的事件。  
  
  > [!NOTE]
  >  用户必须添加到 BAM 事件写入者超级角色。 将用户添加到超级角色时，请务必记住然后将能够在系统中写入到的所有活动用户。  
  
- 如果解决方案需要更好地控制编写的事件，则应使用特定于活动的角色。  
  
  > [!NOTE]
  >  用户必须添加到活动特定的事件写入者角色为每个活动。  
  
  有关配置 BAM 事件写入者角色的详细信息，请参阅[如何确定和活动中设置事件写入者角色](../core/how-to-determine-and-set-event-writer-roles-for-activities.md)。  
  
> [!IMPORTANT]
>  必须是 BizTalk Application Users 组的成员。  
  
 选择要配置 IIS 模拟安全的 BAM WCF 侦听器时使用的用户帐户时应考虑以下方案：  
  
- 自承载：在计算机上可执行文件运行承载 WCF 服务打开。  
  
- WCF 适配器：使用创建的解决方案**Biztalk WCF 服务发布向导**。  
  
- IIS 为宿主：使用 WCF 服务的 IIS 应用程序中托管的解决方案。  
  
  使用下表有助于确定要使用的帐户：  
  
|解决方案类型|若要使用的帐户|  
|-------------------|--------------------|  
|自承载|用于运行保持服务的可执行文件的帐户打开。|  
|WCF 适配器|使用应用程序池标识：这是与包含接收位置的 Vroot 相关联的应用程序池。 当你使用时自动创建此标识**BizTalk WCF 服务发布向导**以发布该站点。 您可以考虑这一种特殊情况的 IIS 承载解决方案。|  
|IIS-hosted|运行 WCF 服务 VRoot/应用程序的应用程序池用户标识。|  
  
## <a name="see-also"></a>请参阅  
 [BAM 侦听器的安全注意事项](../core/security-considerations-for-bam-interceptors.md)