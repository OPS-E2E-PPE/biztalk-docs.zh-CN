---
title: ADMIN-WMI （BizTalk Server 示例文件夹） |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- administering, WMI
- examples, Windows Management Instrumentation (WMI)
- Windows Management Instrumentation (WMI), administering
- Windows Management Instrumentation (WMI), examples
- examples, administering
- administering, examples
ms.assetid: 39e2a6fe-2781-4be2-a152-f5e9960a0faa
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 19d27b2f987ef9ecbd9e7c00e9d149ae26bf7a5a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65360036"
---
# <a name="admin-wmi-biztalk-server-samples-folder"></a><span data-ttu-id="2b66b-102">ADMIN-WMI （BizTalk Server 示例文件夹）</span><span class="sxs-lookup"><span data-stu-id="2b66b-102">Admin-WMI (BizTalk Server Samples Folder)</span></span>
<span data-ttu-id="2b66b-103">Microsoft[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]在其软件开发工具包 (SDK) 包含几个 Microsoft Windows Management Instrumentation (WMI) 管理示例。</span><span class="sxs-lookup"><span data-stu-id="2b66b-103">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] includes several Microsoft Windows Management Instrumentation (WMI) administration samples in its software development kit (SDK).</span></span> <span data-ttu-id="2b66b-104">本部分提供有关每个 WMI 管理示例，说明用于构建和运行示例，以及可以预期的结果所演示的功能的详细的信息。</span><span class="sxs-lookup"><span data-stu-id="2b66b-104">This section provides detailed information about the functionality demonstrated by each WMI administration sample, instructions for building and running the sample, and the results you can expect.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="2b66b-105">如果不需要应在部署后删除的部署脚本。</span><span class="sxs-lookup"><span data-stu-id="2b66b-105">Deployment scripts should be removed after deployment if not needed.</span></span> <span data-ttu-id="2b66b-106">管理脚本和其他必须保持的脚本应受 ACL 并加以密切监视。</span><span class="sxs-lookup"><span data-stu-id="2b66b-106">Administration scripts and other scripts that must remain should be secured by ACL’s and closely monitored.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2b66b-107">本节内容</span><span class="sxs-lookup"><span data-stu-id="2b66b-107">In This Section</span></span>  
  
-   <span data-ttu-id="2b66b-108">[启用接收位置 （BizTalk Server 示例）](../core/enable-receive-location-biztalk-server-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="2b66b-108">[Enable Receive Location (BizTalk Server Sample)](../core/enable-receive-location-biztalk-server-sample.md).</span></span> <span data-ttu-id="2b66b-109">演示如何启用接收位置，并设置该接收位置的入站传输 URL。</span><span class="sxs-lookup"><span data-stu-id="2b66b-109">Demonstrates how to enable a receive location and set the Inbound Transport URL for that receive location.</span></span>  
  
-   <span data-ttu-id="2b66b-110">[登记业务流程 （BizTalk Server 示例）](../core/enlist-orchestration-biztalk-server-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="2b66b-110">[Enlist Orchestration (BizTalk Server Sample)](../core/enlist-orchestration-biztalk-server-sample.md).</span></span> <span data-ttu-id="2b66b-111">演示如何登记到主机的 BizTalk Server 业务流程。</span><span class="sxs-lookup"><span data-stu-id="2b66b-111">Demonstrates how to enlist a BizTalk Server orchestration to a host.</span></span>  
  
-   <span data-ttu-id="2b66b-112">[枚举接收位置 （BizTalk Server 示例）](../core/enumerate-receive-locations-biztalk-server-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="2b66b-112">[Enumerate Receive Locations (BizTalk Server Sample)](../core/enumerate-receive-locations-biztalk-server-sample.md).</span></span> <span data-ttu-id="2b66b-113">演示如何检索详细信息有关一个或多个接收位置。</span><span class="sxs-lookup"><span data-stu-id="2b66b-113">Demonstrates how to retrieve details about one or more receive locations.</span></span>  
  
-   <span data-ttu-id="2b66b-114">[删除接收端口 （BizTalk Server 示例）](../core/remove-receive-port-biztalk-server-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="2b66b-114">[Remove Receive Port (BizTalk Server Sample)](../core/remove-receive-port-biztalk-server-sample.md).</span></span> <span data-ttu-id="2b66b-115">演示如何删除一个或多个接收端口。</span><span class="sxs-lookup"><span data-stu-id="2b66b-115">Demonstrates how to remove one or more receive ports.</span></span>  
  
-   <span data-ttu-id="2b66b-116">[删除发送端口 （BizTalk Server 示例）](../core/remove-send-port-biztalk-server-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="2b66b-116">[Remove Send Port (BizTalk Server Sample)](../core/remove-send-port-biztalk-server-sample.md).</span></span> <span data-ttu-id="2b66b-117">演示如何取消登记和删除一个或多个发送端口。</span><span class="sxs-lookup"><span data-stu-id="2b66b-117">Demonstrates how to unenlist and remove one or more send ports.</span></span>  
  
-   <span data-ttu-id="2b66b-118">[设置发送处理程序属性 （BizTalk Server 示例）](../core/set-send-handler-property-biztalk-server-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="2b66b-118">[Set Send Handler Property (BizTalk Server Sample)](../core/set-send-handler-property-biztalk-server-sample.md).</span></span> <span data-ttu-id="2b66b-119">演示如何设置简单邮件传输协议 (SMTP) 发送处理程序的 XML 配置信息。</span><span class="sxs-lookup"><span data-stu-id="2b66b-119">Demonstrates how to set the XML configuration information for a Simple Mail Transfer Protocol (SMTP) send handler.</span></span>  
  
-   <span data-ttu-id="2b66b-120">[启动发送端口 （BizTalk Server 示例）](../core/start-send-port-biztalk-server-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="2b66b-120">[Start Send Port (BizTalk Server Sample)](../core/start-send-port-biztalk-server-sample.md).</span></span> <span data-ttu-id="2b66b-121">演示如何启动发送端口和使用文件适配器时，设置主传输地址。</span><span class="sxs-lookup"><span data-stu-id="2b66b-121">Demonstrates how to start a send port and set the Primary Transport Address when using the FILE adapter.</span></span>  
  
-   <span data-ttu-id="2b66b-122">[停止业务流程 （BizTalk Server 示例）](../core/stop-orchestration-biztalk-server-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="2b66b-122">[Stop Orchestration (BizTalk Server Sample)](../core/stop-orchestration-biztalk-server-sample.md).</span></span> <span data-ttu-id="2b66b-123">演示如何停止 BizTalk Server 业务流程和 （可选） 若要取消登记它。</span><span class="sxs-lookup"><span data-stu-id="2b66b-123">Demonstrates how to stop a BizTalk Server orchestration and, optionally, to unenlist it.</span></span>