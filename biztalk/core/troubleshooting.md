---
title: 疑难解答和已知问题 |Microsoft 文档
description: 已知问题，僵尸，性能故障排除、 诊断适配器，解决权限、 解决 EDI 和 AS2 和 BizTalk Server 中的详细信息
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ecb934c6-3efa-40b6-949b-a04a73e60b07
caps.latest.revision: 32
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 79364dfed295cf0faac573c080feb171184f2bb0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65321800"
---
# <a name="troubleshooting"></a><span data-ttu-id="6c8b1-103">故障排除</span><span class="sxs-lookup"><span data-stu-id="6c8b1-103">Troubleshooting</span></span>

## <a name="overview"></a><span data-ttu-id="6c8b1-104">概述</span><span class="sxs-lookup"><span data-stu-id="6c8b1-104">Overview</span></span>
<span data-ttu-id="6c8b1-105">Microsoft[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]使使用的或可能取决于多种不同的 Microsoft 技术包括但不是限于 Microsoft [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]，Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，Microsoft [!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)]，Internet Information Services (IIS)，MicrosoftWindows Server 群集时，企业单一登录，和 Windows [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="6c8b1-105">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] makes use of or may depend on several different Microsoft technologies including but not limited to Microsoft [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)], Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], the Microsoft [!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)], Internet Information Services (IIS), Microsoft Windows Server Cluster, Enterprise Single Sign-On, and Windows [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)].</span></span> <span data-ttu-id="6c8b1-106">因为[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]用于许多其他技术，故障排除问题[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]通常会涉及故障排除的基础的技术或正在使用的依赖项。</span><span class="sxs-lookup"><span data-stu-id="6c8b1-106">Because [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is used with so many other technologies, troubleshooting a problem with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] often involves troubleshooting the underlying technology or dependency that is being used.</span></span> <span data-ttu-id="6c8b1-107">本部分提供有关排除特定信息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]问题和进行疑难解答中可能发生的问题的信息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]依赖软件。</span><span class="sxs-lookup"><span data-stu-id="6c8b1-107">This section provides information about troubleshooting specific [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] problems and information about troubleshooting problems that can occur in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] dependency software.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="6c8b1-108">后续步骤</span><span class="sxs-lookup"><span data-stu-id="6c8b1-108">Next steps</span></span> 
  
-   [<span data-ttu-id="6c8b1-109">与 BizTalk Server 的已知的问题</span><span class="sxs-lookup"><span data-stu-id="6c8b1-109">Known Issues with BizTalk Server</span></span>](../core/known-issues-with-biztalk-server.md)  

-   [<span data-ttu-id="6c8b1-110">BizTalk Server 中的僵尸</span><span class="sxs-lookup"><span data-stu-id="6c8b1-110">Zombies in BizTalk Server</span></span>](zombies-in-biztalk-server.md)
  
-   [<span data-ttu-id="6c8b1-111">BizTalk Server 管理疑难解答</span><span class="sxs-lookup"><span data-stu-id="6c8b1-111">Troubleshoot BizTalk Server Administration</span></span>](../core/troubleshooting-biztalk-server-administration.md)  
  
-   [<span data-ttu-id="6c8b1-112">启用 System.Net 日志记录</span><span class="sxs-lookup"><span data-stu-id="6c8b1-112">Enabling System.Net Logging</span></span>](../core/enabling-system-net-logging.md)  
  
-   [<span data-ttu-id="6c8b1-113">解决 BizTalk Server 权限</span><span class="sxs-lookup"><span data-stu-id="6c8b1-113">Troubleshoot BizTalk Server Permissions</span></span>](../core/troubleshooting-biztalk-server-permissions.md)  
  
-   [<span data-ttu-id="6c8b1-114">BizTalk Server 性能故障排除</span><span class="sxs-lookup"><span data-stu-id="6c8b1-114">Troubleshoot BizTalk Server Performance</span></span>](../core/troubleshooting-biztalk-server-performance.md)  
  
-   [<span data-ttu-id="6c8b1-115">解决 BizTalk Server 适配器</span><span class="sxs-lookup"><span data-stu-id="6c8b1-115">Troubleshoot BizTalk Server Adapters</span></span>](../core/troubleshooting-biztalk-server-adapters.md)  
  
-   [<span data-ttu-id="6c8b1-116">对 EDI 和 AS2 解决方案进行故障排除</span><span class="sxs-lookup"><span data-stu-id="6c8b1-116">Troubleshoot EDI and AS2 Solutions</span></span>](../core/troubleshooting-edi-and-as2-solutions.md)  
  
-   [<span data-ttu-id="6c8b1-117">解决 BizTalk Server 依赖项</span><span class="sxs-lookup"><span data-stu-id="6c8b1-117">Troubleshoot BizTalk Server Dependencies</span></span>](../core/troubleshooting-biztalk-server-dependencies.md)  
  
-   [<span data-ttu-id="6c8b1-118">解决配置问题</span><span class="sxs-lookup"><span data-stu-id="6c8b1-118">Troubleshoot Configuration</span></span>](../core/troubleshooting-configuration.md)  
  
-   [<span data-ttu-id="6c8b1-119">获取 BizTalk 进程的内存转储</span><span class="sxs-lookup"><span data-stu-id="6c8b1-119">Get a Memory Dump of a BizTalk Process</span></span>](../core/how-to-capture-a-memory-dump-of-a-biztalk-process.md)  
  
-   [<span data-ttu-id="6c8b1-120">工具和实用程序</span><span class="sxs-lookup"><span data-stu-id="6c8b1-120">Tools and Utilities</span></span>](../core/tools-and-utilities-to-use-for-troubleshooting.md)  
  
-   [<span data-ttu-id="6c8b1-121">解决使用十六进制内容的挂起消息的消息验证失败</span><span class="sxs-lookup"><span data-stu-id="6c8b1-121">Troubleshoot Message Validation Failures using the Hexadecimal Contents of Suspended Messages</span></span>](../core/troubleshoot-message-validation-failures-using-the-hexadecimal-contents.md)

- [<span data-ttu-id="6c8b1-122">事件和错误</span><span class="sxs-lookup"><span data-stu-id="6c8b1-122">Events and Errors</span></span>](events-and-errors2.md)