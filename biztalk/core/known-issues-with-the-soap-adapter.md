---
title: 使用 SOAP 适配器的已知问题 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a3229d73-170d-42b7-bab9-12ae5f2d0fa7
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4b0d27f01efee12e32d201a1a0f7ab9e686088cc
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65329022"
---
# <a name="known-issues-with-the-soap-adapter"></a>SOAP 适配器的已知的问题
本部分包含可能帮助您避免错误的信息。  
  
## <a name="known-issues"></a>已知问题  
  
#### <a name="the-soap-adapter-experiences-poor-performance-or-generates-errors-under-load"></a>SOAP 适配器性能降低或生成负载下的错误  
  
##### <a name="problem"></a>问题  
 SOAP 适配器性能降低或生成负载下的错误  
  
##### <a name="cause"></a>原因  
 由于 SOAP 适配器或影响 SOAP 适配器的依存关系组件的默认配置选项不进行优化，在负载下的性能，将发生此问题。  
  
##### <a name="resolution"></a>解决方法  
 若要解决此问题，请修改 SOAP 适配器或依存关系组件的主题中所述的配置选项[配置参数会影响适配器性能的](../core/configuration-parameters-that-affect-adapter-performance.md)。  
  
#### <a name="the-mimesmime-encoder-and-decoder-pipeline-components-cannot-encode-and-decode-data-processed-by-the-soap-adapter"></a>MIME/SMIME 编码器和解码器管道组件不能进行编码和解码通过 SOAP 适配器处理的数据  
  
##### <a name="problem"></a>问题  
 MIME/SMIME 编码器和解码器管道组件不能进行编码和解码通过 SOAP 适配器处理的数据  
  
##### <a name="cause"></a>原因  
 由于 SOAP 适配器组装和拆装 SOAP 消息的适配器阶段的过程，将发生此问题。  
  
##### <a name="resolution"></a>解决方法  
 若要解决此问题，请使用安全套接字层 (SSL) 来保护通信的 SOAP 适配器处理的消息进行编码。 在发送端，使用**客户端证书指纹**来实现此目的的 SOAP 适配器属性页中的属性。 在接收端，必须配置虚拟目录用于承载 BizTalk Web 服务的 SSL 安全通信。  
  
#### <a name="the-default-appdomain-hosting-the-soap-adapter-gets-unloaded-causing-the-host-process-to-hang"></a>默认值承载 SOAP 适配器的 AppDomain 被卸载，导致主机进程挂起  
  
##### <a name="problem"></a>问题  
 承载 SOAP 适配器的进程挂起，所有其他 Web 服务导致的挂起的过程。 这可能会导致以下错误：  
  
 执行响应 （发送） 管道时出错："未知"源："未知"接收端口：TwoWayLatencyLoopBack_RxPort" URI: "/TwoWayLatencyRxSOAP/TwoWayLatencyWS.asmx" Reason:尝试访问已卸载的 AppDomain。  
  
##### <a name="cause"></a>原因  
 SOAP 适配器在 IIS 进程空间中运行。 如果 IIS AppPool 中存在多个 Web 服务，每个 Web 服务最后会具有其自身的 AppDomain。  
  
 所有消息引擎对象在第一个 AppDomain 中默认情况下的创建 （即。 与第一个 Web 服务相对应的 AppDomain 确定)。 如果第一个 Web 服务的时间出于任何原因长时间处于非活动状态，IIS 将卸载第一个 AppDomain。 在此情况下，宿主进程中的所有服务都变为不可用。  
  
##### <a name="resolution"></a>解决方法  
 若要防止 AppDomain 被卸载，请执行以下过程：  
  
1. 单击**启动**，依次指向**所有程序**，指向**Microsoft BizTalk Server** ，然后单击**BizTalk Server 管理**。  
  
2. 在中**BizTalk Server 管理控制台**，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**平台设置**，然后单击**主机**。  
  
3. 从主机列表中，右键单击所需的主机，然后依次**设置**。  
  
4. 在中**BizTalk 设置仪表板**，检查**独立适配器的默认应用程序域**下**常规**选项卡。  
  
   当执行此操作时，默认值而不是在自己的 Appdomain 的 AppDomain 中创建 BizTalk 消息引擎对象。 因为永远不会卸载默认 AppDomain 时，不会再出现问题。  
  
#### <a name="the-soap-adapter-fails-to-register"></a>SOAP 适配器无法注册  
  
##### <a name="problem"></a>问题  
 BizTalk Server 尝试注册 SOAP （或 HTTP） 适配器时，可能出现以下错误。  
  
 "消息引擎无法注册适配器"SOAP"。 详细信息："注册同一进程内的多个适配器类型不受支持的方案。 例如 HTTP 和 SOAP 接收适配器不能同时存在同一进程中"。  
  
 或  
  
 "消息引擎无法注册适配器"HTTP"。 详细信息："注册同一进程内的多个适配器类型不受支持的方案。  例如 HTTP 和 SOAP 接收适配器不能同时存在同一进程中"。  
  
##### <a name="cause"></a>原因  
 运行时[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]上[!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)]/ IIS 6.x，SOAP 和 HTTP 适配器不能执行在同一进程空间或应用程序池中。  
  
##### <a name="resolution"></a>解决方法  
 如果安装需要相同的 Web 服务器上使用 SOAP 和 HTTP 适配器则必须为每个适配器创建单独的应用程序池。  创建后，每个适配器的虚拟目录每个分配给不同的应用程序池。  
  
> [!NOTE]
>  出现此问题不在 Windows XP 以来在这些操作系统下运行在 IIS 下的不同进程空间中的 SOAP 和 HTTP 适配器 5.x。  SOAP 适配器作为 ASP.Net 应用程序在 aspnet_wp.exe 进程中运行。  HTTP 适配器运行在 dllhost.exe 的专用的进程空间中。  因此这两种适配器都允许用户同时运行同一 Web 服务器上彼此隔离。  
  
## <a name="see-also"></a>请参阅  
 [SOAP 适配器故障排除](../core/troubleshooting-the-soap-adapter.md)