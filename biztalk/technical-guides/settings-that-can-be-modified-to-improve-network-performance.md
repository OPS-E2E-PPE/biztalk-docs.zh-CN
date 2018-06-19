---
title: 可以修改为提高网络性能的设置 |Microsoft 文档
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
ms.openlocfilehash: 8557c8bbe8c0b1c785d6da8d87e8950d3779b8d0
ms.sourcegitcommit: 36350889f318e1f7e0ac9506dc8df794d475bda6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/20/2018
ms.locfileid: "25976323"
---
# <a name="settings-that-can-be-modified-to-improve-network-performance"></a>可以修改为提高网络性能的设置
本主题提供建议的值的说明该影响网络性能。  
  
> [!IMPORTANT]  
>  在完成本指南中的性能测试期间它可以观察到，Windows Server 2008 显示默认情况下优化。 应仅在系统上的效果的仔细的分析后完成修改注册表设置。  
  
## <a name="adjust-the-maxuserport-and-tcptimedwaitdelay-settings"></a>调整 MaxUserPort 和 TcpTimedWaitDelay 设置  
 **MaxUserPort**值控制在应用程序请求从系统的任何可用的用户端口时使用的最大端口号。 通常情况下，生存期较短的端口是从分配的范围内 1025 到 65535 之间。 端口范围现在真正是一组与起始点，并与终结点。 新的默认起始端口为 49152，而默认结束端口为 65535。 此范围是除了通过服务和应用程序使用的已知端口。 可以在每个服务器上修改的服务器使用的端口范围。 你可以按以下方式使用 netsh 命令中，调整此范围：  
  
 **netsh int \<ipv4&#124;ipv6\>设置动态\<tcp&#124;udp\>启动 = 数字 num = 范围**  
  
 此命令设置为 TCP 动态端口范围。 起始端口是**数**，和端口的总数是**范围**。 以下是示例命令： 你可以使用以下 netsh 命令来查看动态端口范围：  
  
-   netsh int ipv4 显示动态 tcp。 若要增加为 tcp v4 的最大允许值范围，请使用以下命令：  
  
     **netsh int ipv4 设置动态 tcp 启动 = 1025 num = 64511**  
  
-   netsh int ipv4 显示动态 udp  
  
-   netsh int ipv6 show 动态 tcp  
  
-   netsh int ipv6 show 动态 udp  
  
 **TcpTimedWaitDelay**值确定的连接在正在关闭时处于 TIME_WAIT 状态的时间长度。 TIME_WAIT 状态连接时，不能重用的套接字对。 这是也称为 2MSL 状态，因为此值应该是两次在网络上的最大的段生存期。 有关详细信息，请参阅[Internet RFC 793](http://go.microsoft.com/fwlink/?LinkId=113719) (超链接"http://go.microsoft.com/fwlink/?LinkId=113719" http://go.microsoft.com/fwlink/?LinkId=113719)。 若要调整 TcpTimedWaitDelay 设置，你必须修改注册表设置，如下所示：  
  
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
  
## <a name="see-also"></a>另请参阅  
 [优化网络性能的通用指南](../technical-guides/general-guidelines-for-improving-network-performance.md)