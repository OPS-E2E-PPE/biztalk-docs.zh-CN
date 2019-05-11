---
title: 附录 B：使用 PeopleSoft 应用程序 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- PeopleSoft, using
- using PeopleSoft application
ms.assetid: 36475836-1d23-4bb4-a3c1-cdd3fff28476
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0a4b82fa41f4df874d5e0a92d53f0b1122dfb5bf
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65359268"
---
# <a name="appendix-b-using-the-peoplesoft-application"></a><span data-ttu-id="79b4e-102">附录 B：使用 PeopleSoft 应用程序</span><span class="sxs-lookup"><span data-stu-id="79b4e-102">Appendix B: Using the PeopleSoft Application</span></span>
<span data-ttu-id="79b4e-103">本部分介绍如何使用者可使用在业务流程测试中的 PeopleSoft 的不同区域。</span><span class="sxs-lookup"><span data-stu-id="79b4e-103">This section describes using different areas of PeopleSoft that could be useful in your orchestration testing.</span></span>  
  
 <span data-ttu-id="79b4e-104">当将 PeopleSoft 用于接收端口时，使用 PeopleTools 来创建 XML 文档。</span><span class="sxs-lookup"><span data-stu-id="79b4e-104">When you use PeopleSoft for receive ports, you use PeopleTools to create an XML document.</span></span> <span data-ttu-id="79b4e-105">没有特殊的要求与 PeopleSoft 交互。</span><span class="sxs-lookup"><span data-stu-id="79b4e-105">Nothing special is required to interact with PeopleSoft.</span></span> <span data-ttu-id="79b4e-106">事件，您必须能够访问**http\\\\:\<主机\>:\<端口\>** 来侦听来自 PeopleSoft 的事件。</span><span class="sxs-lookup"><span data-stu-id="79b4e-106">For an event, you must be able to access to an **http\\\\:\<host\>:\<port\>** to listen for events from PeopleSoft.</span></span> <span data-ttu-id="79b4e-107">如果主机和端口不是可供你的可以通过配置 PeopleSoft Integration Broker 将特定的 HTTP 主机和端口设置。</span><span class="sxs-lookup"><span data-stu-id="79b4e-107">If a host and port is not available to you, you can set up a specific HTTP host and port by configuring the PeopleSoft Integration Broker.</span></span>  
  
 <span data-ttu-id="79b4e-108">若要完成测试 PeopleSoft 接收端口中，[生成 XML 或架构中 PeopleSoft](../core/generating-xml-or-schema-in-peoplesoft.md)讨论如何通过更改 PeopleSoft 环境中的某些内容触发 PeopleSoft 事件。</span><span class="sxs-lookup"><span data-stu-id="79b4e-108">To complete the testing of a PeopleSoft receive port, [Generating XML or Schema in PeopleSoft](../core/generating-xml-or-schema-in-peoplesoft.md) discusses how to trigger a PeopleSoft event by changing something in a PeopleSoft environment.</span></span> <span data-ttu-id="79b4e-109">此更改将激活发送到要监视业务流程中设置的文件夹的 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="79b4e-109">The change activates an XML file that is sent to the folder you set in the orchestration to be monitored.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="79b4e-110">本节内容</span><span class="sxs-lookup"><span data-stu-id="79b4e-110">In This Section</span></span>  
  
-   [<span data-ttu-id="79b4e-111">在 PeopleSoft 中生成 XML 或架构</span><span class="sxs-lookup"><span data-stu-id="79b4e-111">Generating XML or Schema in PeopleSoft</span></span>](../core/generating-xml-or-schema-in-peoplesoft.md)  
  
-   [<span data-ttu-id="79b4e-112">创建 PeopleSoft HTTP 主机和端口</span><span class="sxs-lookup"><span data-stu-id="79b4e-112">Creating a PeopleSoft HTTP Host and Port</span></span>](../core/creating-a-peoplesoft-http-host-and-port.md)