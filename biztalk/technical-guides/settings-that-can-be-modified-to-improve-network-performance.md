---
title: 可以修改为提高网络性能的设置 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: eb6aacc3-e697-4cc9-b937-73a2f54e733b
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 363597ca798abcaa4a75a7c1c1df8568b439001d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65278984"
---
# <a name="settings-that-can-be-modified-to-improve-network-performance"></a>可以修改为提高网络性能的设置
本主题提供的建议值说明网络性能的影响。  
  
> [!IMPORTANT]  
>  在完成本指南中的性能测试期间观察到 Windows Server 2008 会显示默认情况下优化。 仅应在系统上的效果仔细分析之后完成修改注册表设置。  
  
## <a name="adjust-the-maxuserport-and-tcptimedwaitdelay-settings"></a>调整 MaxUserPort 以及 TcpTimedWaitDelay 设置  
 **MaxUserPort**值控制应用程序从系统请求任何可用用户端口时使用的最大端口号。 通常情况下，短期分配端口的范围中从 1025 到 65535 之间。 端口范围现在真正是一个范围的起始点和终结点。 新的默认起始端口为 49152，而默认结束端口为 65535。 此范围是由服务和应用程序使用的已知端口的补充。 每个服务器上，可以修改服务器使用的端口范围。 按如下所示使用 netsh 命令时，调整此范围内：  
  
 **netsh int \<ipv4&#124;ipv6\> set dynamicport \<tcp&#124;udp\> start=number num=range**  
  
 此命令设置 TCP 动态端口范围。 起始端口是**数量**，以及端口总数**范围**。 以下是示例命令：可以使用以下 netsh 命令来查看动态端口范围：  
  
- netsh int ipv4 显示动态 tcp。 若要增加到 tcp v4 的最大允许值的范围，请使用以下命令：  
  
   **netsh int ipv4 set dynamicport tcp start=1025 num=64511**  
  
- netsh int ipv4 显示动态 udp  
  
- netsh int ipv6 显示动态 tcp  
  
- netsh int ipv6 显示动态 udp  
  
  **TcpTimedWaitDelay**值确定的一个连接处于 TIME_WAIT 状态正在关闭时的时间长度。 当连接处于 TIME_WAIT 状态时，则不能重复使用套接字对。 这是也称为 2MSL 状态，因为值应该是在网络上最大段生命周期的两次。 有关详细信息，请参阅[Internet RFC 793](http://go.microsoft.com/fwlink/?LinkId=113719) (超链接"<http://go.microsoft.com/fwlink/?LinkId=113719>" <http://go.microsoft.com/fwlink/?LinkId=113719>)。 若要调整 TcpTimedWaitDelay 设置，您必须修改注册表设置，如下所示：  
  
###  
  
|||  
|-|-|  
|密钥：|HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\Tcpip\Parameters|  
|值：|TcpTimedWaitDelay|  
|数据类型：|REG_DWORD|  
|范围：|30-300 （十进制）|  
|默认值：|0x78 (120 十进制)|  
|建议的值：|30|  
|默认情况下存在值？|**不**，需要添加。|  
  
## <a name="see-also"></a>请参阅  
 [优化网络性能的通用指南](../technical-guides/general-guidelines-for-improving-network-performance.md)