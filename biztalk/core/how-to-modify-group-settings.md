---
title: 更新组设置 |Microsoft Docs
description: 更改使用 BizTalk Server 管理的组的性能设置
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fe0cbeb8-23d6-45cf-8535-c989914f5124
caps.latest.revision: 24
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 72c0af2a97d5199ae765a520dea855665296d57c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65336123"
---
# <a name="how-to-update-the-biztalk-group-settings"></a>如何更新 BizTalk 组设置
使用设置仪表板，可以修改给定的 BizTalk 组中的所有计算机上使用的配置信息。 本主题提供了修改中的组级别性能设置的分步过程[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 这些设置是适用于给定组中的所有计算机。  

> [!NOTE]
>  此外可以修改的主机和主机实例设置。 有关详细信息，请参阅[如何修改主机设置](../core/how-to-modify-host-settings.md)并[如何修改主机实例设置](../core/how-to-modify-host-instance-settings.md)。  

 可以将当前的 BizTalk Server 设置导出到 XML 文件。 更高版本，可以导入设置仪表板，而不是设置新值的这些设置。 有关导入或导出的信息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]设置，请参阅[导入或导出 BizTalk 设置使用设置仪表板](how-to-import-biztalk-settings-using-settings-dashboard.md)并[导入或导出 BizTalk 设置使用 BTSTask](how-to-import-biztalk-settings-using-btstask.md)。 

## <a name="prerequisites"></a>先决条件  
 若要执行此操作，必须以 BizTalk Server Administrators 组的成员的身份登录。  

## <a name="update-the-group-level-settings"></a>更新组级别设置  

1. 在中**BizTalk Server 管理控制台**，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，右键单击**BizTalk 组**，然后单击**设置**。  

2. 在中**BizTalk 设置仪表板**对话框中，在**组**页上，执行以下操作：  


   |                       使用此选项                        |                                                                                                                                                                                          执行的操作                                                                                                                                                                                           |          边界值          | 默认值 |                                                升级逻辑                                                |
   |-------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------|---------------|-------------------------------------------------------------------------------------------------------------|
   |          **配置刷新间隔**           |                                                                                                                        将间隔设置在其中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]刷新消息配置。                                                                                                                        |             1 - 43200             |       -       |                                                      -                                                      |
   |              **消息批处理阈值**              |                                                                                                                                    如果传入消息批的总大小超过此值，它是拆分为较小的批，处理。                                                                                                                                    |           1 - 10000000            |    102400     | 复制 HKEY_LOCAL_MACHINE\Software\Microsoft\BizTalk Server\3.0\Administration\TransformThreshold 值 |
   |                **大消息大小**                 |                                                                                                                                       设置触发流式处理批中和/或在转换期间的单个消息的阈值大小。                                                                                                                                       |           1 - 10000000            |    1000000    |           最大的现有**大消息大小**并**LargeMessageFragmentSize**值。           |
   |              **跟踪和报告**               |                                                                                                                                                                                                                                                                                                                                                                                               |                 -                 |       -       |                                                      -                                                      |
   | **消息框性能计数器采样间隔** |                                                                       设置刷新性能计数器的间隔。<br /><br /> 间隔能负载上数据库与最新的计数器。 更高版本的值表示不经常更新的数据，因此数据库上的较小负载。                                                                        | 1 – 最大值类型为 Integer |       -       |               如果存在在 BizTalk 组中的任何计算机上的最大值。 如果没有，默认值。                |
   |            **启用组级别跟踪**            | 选择此选项可启用组级别上的 BizTalk Server 跟踪。<br /><br /> 关闭全局跟踪会禁用整个的跟踪侦听器[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]组。 这意味着，BizTalk Server 将不跟踪其跟踪表中的事件。 **注意：** 此设置不会影响 BAM 跟踪。 |              On、 Off              |      On       |                                                      -                                                      |


3. 单击**应用**以应用修改并转到另一个选项卡。或单击**确定**应用所做的修改并退出设置仪表板。  

   > [!NOTE]
   >  若要还原默认设置，请单击**还原为默认值**。  

## <a name="see-also"></a>请参阅  
 [使用设置仪表板进行 BizTalk Server 性能调整](../core/using-settings-dashboard-for-biztalk-server-performance-tuning.md)