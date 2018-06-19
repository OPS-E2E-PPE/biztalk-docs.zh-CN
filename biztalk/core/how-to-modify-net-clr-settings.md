---
title: 如何修改.NET CLR 设置 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- Bts10.settings.HostInstanceCLR
ms.assetid: 085743d8-27a6-4d8b-98c7-bb5b5c75848c
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d134faf06aebbb24cafd716722d63172a5ceb68b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22254293"
---
# <a name="how-to-modify-net-clr-settings"></a>如何修改 .NET CLR 设置
若要更新与 BizTalk 主机的实例相关联的 .NET 线程池中可用的 Windows 线程数，可以使用“BizTalk 设置仪表板”修改相应的公共语言运行时 (CLR) Hosting 值。 本主题提供了修改这些设置的分步过程。  
  
## <a name="prerequisites"></a>先决条件  
 若要执行此操作，则必须以 BizTalk Server Administrators 组成员的身份登录。  
  
### <a name="to-modify-the-net-clr-settings-of-a-host-instance"></a>修改主机实例的 .NET CLR 设置  
  
1.  在**BizTalk Server 管理控制台**，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，右键单击**BizTalk 组**，然后单击**设置**。  
  
2.  在**BizTalk 设置仪表板**对话框中，在**主机实例**选项卡上，单击 **.NET CLR**选项卡。  
  
3.  执行以下操作，单击**应用**应用修改再转到另一个选项卡。或单击**确定**应用进行修改并退出设置仪表板。  
  
    |使用此选项|执行的操作|边界值|默认值|升级逻辑|  
    |--------------|----------------|---------------------|-------------------|-------------------|  
    |**主机实例**|从下拉框中，在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 运行时计算机上选择正在运行的主机实例。|-|-|-|  
  
     **线程处理设置**  
  
    |使用此选项|执行的操作|边界值|默认值|升级逻辑|  
    |--------------|----------------|---------------------|-------------------|-------------------|  
    |**最大值。工作线程**|指定 .NET CLR 工作线程的最大数量。|[最小工作线程，500]|25|将主机实例注册表设置迁移到主机实例设置，忽略 Version、Flavor、Flags 和 MinCompletionPortThreads。|  
    |**最小工作线程**|指定 .NET CLR 工作线程的最小数量。|[0, 500]|5|将主机实例注册表设置迁移到主机实例设置，忽略 Version、Flavor、Flags 和 MinCompletionPortThreads。|  
    |**最大值。IO 线程**|指定 IO 线程的最大数量。|[最小 IO 线程，1000]|250|将主机实例注册表设置迁移到主机实例设置，忽略 Version、Flavor、Flags 和 MinCompletionPortThreads。|  
    |**最小值。IO 线程**|指定 IO 线程的最小数量。|[0, 1000]|25|将主机实例注册表设置迁移到主机实例设置，忽略 Version、Flavor、Flags 和 MinCompletionPortThreads。|  
  
     .NET CLR 设置因 CPU 核心而异。  
  
    > [!NOTE]
    >  若要还原默认设置，请单击**还原为默认值**。  
  
    > [!NOTE]
    >  **工作线程**用于处理排队的工作项和**I/O 线程**I/O 完成端口来处理已完成的异步 I/O 请求与关联的专用的回调线程。  
  
    > [!NOTE]
    >  如果 BizTalk 升级从早期版本，在 HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\BTSSvc$ 值*主机名*\CLR 将在设置仪表板中设置宿主注册表项。  
  
## <a name="see-also"></a>另请参阅  
 [如何修改主机实例设置](../core/how-to-modify-host-instance-settings.md)