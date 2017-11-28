---
title: "附录 b： 使用 PeopleSoft 应用程序 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- PeopleSoft, using
- using PeopleSoft application
ms.assetid: 36475836-1d23-4bb4-a3c1-cdd3fff28476
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3ff5c7b2b15c709064174371f1fcab9beb95e42d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="appendix-b-using-the-peoplesoft-application"></a><span data-ttu-id="fa099-102">附录 b： 使用 PeopleSoft 应用程序</span><span class="sxs-lookup"><span data-stu-id="fa099-102">Appendix B: Using the PeopleSoft Application</span></span>
<span data-ttu-id="fa099-103">本部分介绍使用 PeopleSoft 的不同区域，以便可以在业务流程测试中发挥作用。</span><span class="sxs-lookup"><span data-stu-id="fa099-103">This section describes using different areas of PeopleSoft that could be useful in your orchestration testing.</span></span>  
  
 <span data-ttu-id="fa099-104">将 PeopleSoft 用于接收端口时，使用 PeopleTools 来创建 XML 文档。</span><span class="sxs-lookup"><span data-stu-id="fa099-104">When you use PeopleSoft for receive ports, you use PeopleTools to create an XML document.</span></span> <span data-ttu-id="fa099-105">与 PeopleSoft 交互没有特殊的要求。</span><span class="sxs-lookup"><span data-stu-id="fa099-105">Nothing special is required to interact with PeopleSoft.</span></span> <span data-ttu-id="fa099-106">事件，你必须能够访问**http\\\\:\<主机 >:\<端口 >**以侦听来自 PeopleSoft 事件。</span><span class="sxs-lookup"><span data-stu-id="fa099-106">For an event, you must be able to access to an **http\\\\:\<host>:\<port>** to listen for events from PeopleSoft.</span></span> <span data-ttu-id="fa099-107">如果您无法使用主机和端口，则可以通过配置 PeopleSoft Integration Broker 设置特定的 HTTP 主机和端口。</span><span class="sxs-lookup"><span data-stu-id="fa099-107">If a host and port is not available to you, you can set up a specific HTTP host and port by configuring the PeopleSoft Integration Broker.</span></span>  
  
 <span data-ttu-id="fa099-108">若要完成测试 PeopleSoft 接收端口，[生成 XML 或架构中 PeopleSoft](../core/generating-xml-or-schema-in-peoplesoft.md)讨论如何通过更改 PeopleSoft 环境中的一些东西触发 PeopleSoft 事件。</span><span class="sxs-lookup"><span data-stu-id="fa099-108">To complete the testing of a PeopleSoft receive port, [Generating XML or Schema in PeopleSoft](../core/generating-xml-or-schema-in-peoplesoft.md) discusses how to trigger a PeopleSoft event by changing something in a PeopleSoft environment.</span></span> <span data-ttu-id="fa099-109">此更改将激活发送到文件夹（在要监视的业务流程中设置）中的 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="fa099-109">The change activates an XML file that is sent to the folder you set in the orchestration to be monitored.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="fa099-110">本节内容</span><span class="sxs-lookup"><span data-stu-id="fa099-110">In This Section</span></span>  
  
-   [<span data-ttu-id="fa099-111">生成 XML 或架构中 PeopleSoft</span><span class="sxs-lookup"><span data-stu-id="fa099-111">Generating XML or Schema in PeopleSoft</span></span>](../core/generating-xml-or-schema-in-peoplesoft.md)  
  
-   [<span data-ttu-id="fa099-112">创建 PeopleSoft HTTP 主机和端口</span><span class="sxs-lookup"><span data-stu-id="fa099-112">Creating a PeopleSoft HTTP Host and Port</span></span>](../core/creating-a-peoplesoft-http-host-and-port.md)