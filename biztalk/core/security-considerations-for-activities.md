---
title: "有关活动的安全注意事项 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2fc49afd-a1c3-4ac7-8b89-11be667221e2
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 26ea453b24ac3e8df25e7a4da98f27731f3828be
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="security-considerations-for-activities"></a>有关活动的安全注意事项
侦听 WCF 适配器时所使用的安全角色与用于其他 BAM 解决方案的安全角色相同。 侦听 WCF 适配器时需要考虑的其他注意事项还包括选择要使用的正确的用户和事件写入者角色。  
  
 当使用 WCF 服务和 WCF 适配器时，所有与 BAM 相关的数据将由选定的角色写入 BAM 主导入数据库中。  
  
 通过对您的解决方案进行评估，您可以选择合适的用户角色配置：  
  
-   如果您的解决方案需要多个由多个不同类型活动所跟踪的新服务，且这些服务均运行在同一用户帐户下，则最好使用 BAM_EVENT_WRITER 超级角色来写入侦听到的事件。  
  
    > [!NOTE]
    >  用户必须添加到 BAM 事件写入者超级角色。 请记住，当将用户添加到超级角色之后，用户将能够写入系统中的所有活动，这一点至关重要。  
  
-   如果您的解决方案需要对写入的事件拥有更大的控制权，则应使用特定于活动的角色。  
  
    > [!NOTE]
    >  对于每个活动，必须将用户添加到特定于活动的事件写入者角色中。  
  
 有关配置 BAM 事件写入者角色的详细信息，请参阅[如何确定和活动设置事件的编写器角色](../core/how-to-determine-and-set-event-writer-roles-for-activities.md)。  
  
> [!IMPORTANT]
>  你必须是 BizTalk 应用程序用户组的成员。  
  
 若要配置针对 IIS 模拟安全的 BAM WCF 侦听器，在选择用于该目的的用户帐户时应考虑以下情况：  
  
-   自承载： 在计算机上可执行文件运行，承载 WCF 服务打开。  
  
-   WCF 适配器： 使用创建的解决方案**Biztalk WCF 服务发布向导**。  
  
-   承载的 IIS： 使用 WCF 服务的 IIS 应用程序中托管的解决方案。  
  
 请用下表帮助您确定要使用的帐户：  
  
|解决方案类型|要使用的帐户|  
|-------------------|--------------------|  
|自宿主|用于运行保持服务打开的可执行文件的帐户。|  
|WCF 适配器|使用应用程序池标识： 这是与 Vroot 保存接收位置的关联应用程序池。 当你使用自动创建此标识**BizTalk WCF 服务发布向导**以发布站点。 您可以把这种情况看作是以 IIS 为宿主的解决方案的特殊情况。|  
|以 IIS 为宿主|运行 WCF 服务 VRoot/应用程序的 AppPool 用户的标识。|  
  
## <a name="see-also"></a>另请参阅  
 [BAM 拦截器的安全注意事项](../core/security-considerations-for-bam-interceptors.md)