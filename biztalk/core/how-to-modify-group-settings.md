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
ms.openlocfilehash: a22bdc81d3db5a9b64d500d90c428339c0ebfc09
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36966670"
---
# <a name="how-to-update-the-biztalk-group-settings"></a>如何更新 BizTalk 组设置
使用“设置仪表板”，你可以修改给定的 BizTalk 组中所有计算机上使用的配置信息。 本主题提供了修改 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中组级别性能设置的分步过程。 这些设置适用于给定组中的所有计算机。  

> [!NOTE]
>  你还可以修改主机和主机实例设置。 有关详细信息，请参阅[如何修改主机设置](../core/how-to-modify-host-settings.md)并[如何修改主机实例设置](../core/how-to-modify-host-instance-settings.md)。  

 可以将当前的 BizTalk Server 设置导出到 XML 文件。 然后，将这些设置导入到“设置仪表板”，而不是设置新值。 有关导入或导出的信息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]设置，请参阅[导入或导出 BizTalk 设置使用设置仪表板](how-to-import-biztalk-settings-using-settings-dashboard.md)并[导入或导出 BizTalk 设置使用 BTSTask](how-to-import-biztalk-settings-using-btstask.md)。 

## <a name="prerequisites"></a>必要條件  
 若要执行此操作，必须以 BizTalk Server Administrators 组的成员的身份登录。  

## <a name="update-the-group-level-settings"></a>更新组级别设置  

1. 在中**BizTalk Server 管理控制台**，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，右键单击**BizTalk 组**，然后单击**设置**。  

2. 在中**BizTalk 设置仪表板**对话框中，在**组**页上，执行以下操作：  


   |                       使用此选项                        |                                                                                                                                                                                          执行的操作                                                                                                                                                                                           |          边界值          | 默认值 |                                                升级逻辑                                                |
   |-------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------|---------------|-------------------------------------------------------------------------------------------------------------|
   |          **配置刷新间隔**           |                                                                                                                        设置 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 刷新消息配置的间隔。                                                                                                                        |             1 - 43200             |       -       |                                                      -                                                      |
   |              **消息批处理阈值**              |                                                                                                                                    如果传入消息批的总大小超过此值，则会将其分为较小的批进行处理。                                                                                                                                    |           1 - 10000000            |    102400     | 复制 HKEY_LOCAL_MACHINE\Software\Microsoft\BizTalk Server\3.0\Administration\TransformThreshold 值 |
   |                **大消息大小**                 |                                                                                                                                       设置在批中和/或在转换期间触发流的单个消息的阈值大小。                                                                                                                                       |           1 - 10000000            |    1000000    |           最大的现有**大消息大小**并**LargeMessageFragmentSize**值。           |
   |              **跟踪和报告**               |                                                                                                                                                                                                                                                                                                                                                                                               |                 -                 |       -       |                                                      -                                                      |
   | **消息框性能计数器采样间隔** |                                                                       设置刷新性能计数器的时间间隔。<br /><br /> 该时间间隔会在数据库的负载与最新的计数器之间进行权衡。 该值越大，就意味着更新数据的频率越低，因而数据库的负载也就越小。                                                                        | 1 – Integer 类型的最大值 |       -       |               BizTalk 组（如果存在）中任何计算机上的最大值。 如果不存在，则为默认值。                |
   |            **启用组级别跟踪**            | 选择此选项可打开 BizTalk Server 的组级别跟踪。<br /><br /> 关闭全局跟踪会禁用整个 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 组的跟踪侦听器。 这意味着 BizTalk Server 将不跟踪其跟踪表中的事件。 **注意：** 此设置不会影响 BAM 跟踪。 |              On、 Off              |      On       |                                                      -                                                      |


3. 单击**应用**以应用修改并转到另一个选项卡。或单击**确定**应用所做的修改并退出设置仪表板。  

   > [!NOTE]
   >  若要还原默认设置，请单击**还原为默认值**。  

## <a name="see-also"></a>请参阅  
 [使用设置仪表板进行 BizTalk Server 性能调整](../core/using-settings-dashboard-for-biztalk-server-performance-tuning.md)