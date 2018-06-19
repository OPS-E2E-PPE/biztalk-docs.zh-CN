---
title: 管理员-WMI （BizTalk Server 示例文件夹中） |Microsoft 文档
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
ms.openlocfilehash: 19a8698bbe916d86909005ff77c9b1eeea11604f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22230069"
---
# <a name="admin-wmi-biztalk-server-samples-folder"></a><span data-ttu-id="88d40-102">管理员-WMI （BizTalk Server 示例文件夹中）</span><span class="sxs-lookup"><span data-stu-id="88d40-102">Admin-WMI (BizTalk Server Samples Folder)</span></span>
<span data-ttu-id="88d40-103">Microsoft[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]其软件开发工具包 (SDK) 中包含多个 Microsoft Windows Management Instrumentation (WMI) 管理示例。</span><span class="sxs-lookup"><span data-stu-id="88d40-103">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] includes several Microsoft Windows Management Instrumentation (WMI) administration samples in its software development kit (SDK).</span></span> <span data-ttu-id="88d40-104">本部分提供每个 WMI 管理示例所演示功能的详细信息、生成和运行每个示例的说明以及预期得到的结果。</span><span class="sxs-lookup"><span data-stu-id="88d40-104">This section provides detailed information about the functionality demonstrated by each WMI administration sample, instructions for building and running the sample, and the results you can expect.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="88d40-105">部署后，如果不再需要部署脚本，则应将其删除。</span><span class="sxs-lookup"><span data-stu-id="88d40-105">Deployment scripts should be removed after deployment if not needed.</span></span> <span data-ttu-id="88d40-106">应通过 ACL 确保必须保留的管理脚本和其他脚本的安全并加以密切监视。</span><span class="sxs-lookup"><span data-stu-id="88d40-106">Administration scripts and other scripts that must remain should be secured by ACL’s and closely monitored.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="88d40-107">本节内容</span><span class="sxs-lookup"><span data-stu-id="88d40-107">In This Section</span></span>  
  
-   <span data-ttu-id="88d40-108">[启用接收位置 （BizTalk Server 示例）](../core/enable-receive-location-biztalk-server-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="88d40-108">[Enable Receive Location (BizTalk Server Sample)](../core/enable-receive-location-biztalk-server-sample.md).</span></span> <span data-ttu-id="88d40-109">演示如何启用某接收位置和为此接受位置设置入站传输 URL。</span><span class="sxs-lookup"><span data-stu-id="88d40-109">Demonstrates how to enable a receive location and set the Inbound Transport URL for that receive location.</span></span>  
  
-   <span data-ttu-id="88d40-110">[登记业务流程 （BizTalk Server 示例）](../core/enlist-orchestration-biztalk-server-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="88d40-110">[Enlist Orchestration (BizTalk Server Sample)](../core/enlist-orchestration-biztalk-server-sample.md).</span></span> <span data-ttu-id="88d40-111">演示如何向主机登记 BizTalk Server 业务流程。</span><span class="sxs-lookup"><span data-stu-id="88d40-111">Demonstrates how to enlist a BizTalk Server orchestration to a host.</span></span>  
  
-   <span data-ttu-id="88d40-112">[枚举接收位置 （BizTalk Server 示例）](../core/enumerate-receive-locations-biztalk-server-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="88d40-112">[Enumerate Receive Locations (BizTalk Server Sample)](../core/enumerate-receive-locations-biztalk-server-sample.md).</span></span> <span data-ttu-id="88d40-113">演示如何检索有关一个或多个接收位置的详细信息。</span><span class="sxs-lookup"><span data-stu-id="88d40-113">Demonstrates how to retrieve details about one or more receive locations.</span></span>  
  
-   <span data-ttu-id="88d40-114">[删除接收端口 （BizTalk Server 示例）](../core/remove-receive-port-biztalk-server-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="88d40-114">[Remove Receive Port (BizTalk Server Sample)](../core/remove-receive-port-biztalk-server-sample.md).</span></span> <span data-ttu-id="88d40-115">演示如何删除一个或多个接收端口。</span><span class="sxs-lookup"><span data-stu-id="88d40-115">Demonstrates how to remove one or more receive ports.</span></span>  
  
-   <span data-ttu-id="88d40-116">[删除发送端口 （BizTalk Server 示例）](../core/remove-send-port-biztalk-server-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="88d40-116">[Remove Send Port (BizTalk Server Sample)](../core/remove-send-port-biztalk-server-sample.md).</span></span> <span data-ttu-id="88d40-117">演示如何取消登记和删除一个或多个发送端口。</span><span class="sxs-lookup"><span data-stu-id="88d40-117">Demonstrates how to unenlist and remove one or more send ports.</span></span>  
  
-   <span data-ttu-id="88d40-118">[设置发送处理程序属性 （BizTalk Server 示例）](../core/set-send-handler-property-biztalk-server-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="88d40-118">[Set Send Handler Property (BizTalk Server Sample)](../core/set-send-handler-property-biztalk-server-sample.md).</span></span> <span data-ttu-id="88d40-119">演示如何为简单邮件传输协议 (SMTP) 发送处理程序设置 XML 配置信息。</span><span class="sxs-lookup"><span data-stu-id="88d40-119">Demonstrates how to set the XML configuration information for a Simple Mail Transfer Protocol (SMTP) send handler.</span></span>  
  
-   <span data-ttu-id="88d40-120">[开始发送端口 （BizTalk Server 示例）](../core/start-send-port-biztalk-server-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="88d40-120">[Start Send Port (BizTalk Server Sample)](../core/start-send-port-biztalk-server-sample.md).</span></span> <span data-ttu-id="88d40-121">演示如何在使用 FILE 适配器时启动发送端口和设置主传输地址。</span><span class="sxs-lookup"><span data-stu-id="88d40-121">Demonstrates how to start a send port and set the Primary Transport Address when using the FILE adapter.</span></span>  
  
-   <span data-ttu-id="88d40-122">[停止业务流程 （BizTalk Server 示例）](../core/stop-orchestration-biztalk-server-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="88d40-122">[Stop Orchestration (BizTalk Server Sample)](../core/stop-orchestration-biztalk-server-sample.md).</span></span> <span data-ttu-id="88d40-123">演示如何停止 BizTalk Server 业务流程和对其取消登记，后者可选。</span><span class="sxs-lookup"><span data-stu-id="88d40-123">Demonstrates how to stop a BizTalk Server orchestration and, optionally, to unenlist it.</span></span>