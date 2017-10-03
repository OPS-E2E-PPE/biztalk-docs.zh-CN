---
title: "已知问题的 SOAP 适配器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a3229d73-170d-42b7-bab9-12ae5f2d0fa7
caps.latest.revision: "18"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 671510c6901fc399580ab73018e67eadc86f7212
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="known-issues-with-the-soap-adapter"></a>SOAP 适配器的已知问题
本部分包含可帮助你避免出现错误的信息。  
  
## <a name="known-issues"></a>已知问题  
  
#### <a name="the-soap-adapter-experiences-poor-performance-or-generates-errors-under-load"></a>SOAP 适配器在负载下性能降低或生成错误  
  
##### <a name="problem"></a>问题  
 SOAP 适配器在负载下性能降低或生成错误  
  
##### <a name="cause"></a>原因  
 发生这一问题的原因是 SOAP 适配器的默认配置选项或影响 SOAP 适配器的依存关系组件的默认配置选项未针对负载下的性能进行优化。  
  
##### <a name="resolution"></a>解决方法  
 若要解决此问题，请修改 SOAP 适配器或主题中所述的依赖项组件的配置选项[配置参数会影响适配器性能](../core/configuration-parameters-that-affect-adapter-performance.md)。  
  
#### <a name="the-mimesmime-encoder-and-decoder-pipeline-components-cannot-encode-and-decode-data-processed-by-the-soap-adapter"></a>MIME/SMIME 编码器和解码器管道组件无法对 SOAP 适配器处理的数据进行编码和解码  
  
##### <a name="problem"></a>问题  
 MIME/SMIME 编码器和解码器管道组件无法对 SOAP 适配器处理的数据进行编码和解码  
  
##### <a name="cause"></a>原因  
 发生这一问题的原因是 SOAP 适配器在流程的适配器阶段组装和拆装 SOAP 消息。  
  
##### <a name="resolution"></a>解决方法  
 若要解决此问题，请使用安全套接字层 (SSL) 保障通信的安全，以便对 SOAP 适配器处理的信息进行编码。 在发送端，使用**客户端证书指纹**来实现此目的的 SOAP 适配器属性页中的属性。 在接收端，必须为 SSL 安全通信配置 BizTalk Web Services 的宿主虚拟目录。  
  
#### <a name="the-default-appdomain-hosting-the-soap-adapter-gets-unloaded-causing-the-host-process-to-hang"></a>承载 SOAP 适配器的默认 AppDomain 被卸载，导致主机进程挂起  
  
##### <a name="problem"></a>问题  
 承载 SOAP 适配器的进程挂起，导致进程中的所有其他 Web Services 挂起。 这可能导致以下错误：  
  
 执行 response(send) 管道失败:"未知"的源:"未知"接收端口:: TwoWayLatencyLoopBack_RxPort"URI:"/ TwoWayLatencyRxSOAP/TwoWayLatencyWS.asmx"原因： 尝试访问已卸载的 AppDomain。  
  
##### <a name="cause"></a>原因  
 SOAP 适配器在 IIS 进程空间中运行。 如果 IIS AppPool 中存在一个以上的 Web Services，则每个 Web Services 最后会具有自己的 AppDomain。  
  
 默认情况下可以在第一个 AppDomain 中中创建所有消息传递引擎对象 （即。 与第一个 Web 服务相对应的 AppDomain 确定)。 如果第一个 Web Services 出于任何原因在很长的一段时间内是不活动的，IIS 将卸载第一个 AppDomain。 出现这样的情况时，承载进程中的所有服务都不能使用。  
  
##### <a name="resolution"></a>解决方法  
 若要防止卸载 AppDomain，请执行以下过程：  
  
1.  单击**启动**，指向**所有程序**，指向**Microsoft BizTalk Server** ，然后单击**BizTalk Server 管理**。  
  
2.  在**BizTalk Server 管理控制台**，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**平台设置**，然后单击**主机**。  
  
3.  从主机列表中，右键单击所需的主机，并依次**设置**。  
  
4.  在**BizTalk 设置仪表板**，检查**独立的适配器的默认应用程序域**下**常规**选项卡。  
  
 执行此操作后，BizTalk 消息引擎对象在默认的 AppDomain 中创建，而不是在自己的 AppDomain 中创建。 因为默认的 AppDomain 永不被卸载，就不会再出现这样的问题了。  
  
#### <a name="the-soap-adapter-fails-to-register"></a>SOAP 适配器无法注册  
  
##### <a name="problem"></a>问题  
 BizTalk Server 尝试注册 SOAP（或 HTTP）适配器时，可能出现以下错误。  
  
 “The Messaging Engine failed to register an adapter SOAP”（消息引擎无法注册适配器 SOAP。） 详细信息:"注册相同的进程内的多个适配器类型不是受支持的方案。 “For e.g. HTTP and SOAP receive adapters cannot co-exist in the same process.”（例如，HTTP 和 SOAP 接收适配器不能在同一个进程中共存。）  
  
 或  
  
 “The Messaging Engine failed to register an adapter HTTP”（消息引擎无法注册适配器 HTTP。） 详细信息:"注册相同的进程内的多个适配器类型不是受支持的方案。  “For e.g. HTTP and SOAP receive adapters cannot co-exist in the same process.”（例如，HTTP 和 SOAP 接收适配器不能在同一个进程中共存。）  
  
##### <a name="cause"></a>原因  
 在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] / IIS 6.x 上运行 [!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)] 时，SOAP 和 HTTP 适配器不能在同一个进程空间或应用程序池中执行。  
  
##### <a name="resolution"></a>解决方法  
 如果安装需要在一个 Web 服务器上同时使用 SOAP 和 HTTP 适配器，则必须为每个适配器创建单独的应用程序池。  创建后，每个适配器的虚拟目录被分别分配给不同的应用程序池。  
  
> [!NOTE]
>  在 Windows XP 下不会出现此问题，因为在这些操作系统下，SOAP 和 HTTP 适配器运行在 IIS 5.x 下的不同进程空间中。  SOAP 适配器作为 ASP.Net 应用程序运行在 aspnet_wp.exe 进程中。  HTTP 适配器运行在 dllhost.exe 的专用进程空间中。  因此，这两个适配器是相互隔离的，可以同时在一个 Web 服务器上运行。  
  
## <a name="see-also"></a>另请参阅  
 [故障排除 SOAP 适配器](../core/troubleshooting-the-soap-adapter.md)