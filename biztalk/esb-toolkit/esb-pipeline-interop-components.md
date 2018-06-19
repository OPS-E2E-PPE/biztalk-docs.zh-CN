---
title: ESB 管道互操作组件 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 25f9fb9d-d3d4-4df8-8e81-38b432f42ccf
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ccf4d4353e6928b998d31e8096ee642cd80bb60a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22294125"
---
# <a name="esb-pipeline-interop-components"></a><span data-ttu-id="5286e-102">ESB 管道互操作组件</span><span class="sxs-lookup"><span data-stu-id="5286e-102">ESB Pipeline Interop Components</span></span>
<span data-ttu-id="5286e-103">[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]提供支持组件和服务，其中包括：</span><span class="sxs-lookup"><span data-stu-id="5286e-103">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] provides support components and services, including the following:</span></span>  
  
-   <span data-ttu-id="5286e-104">**JMS 管道组件。**</span><span class="sxs-lookup"><span data-stu-id="5286e-104">**JMS pipeline components.**</span></span> <span data-ttu-id="5286e-105">这些组件识别、 验证和公开元数据和符合使用 IBM MQ 系列消息传递系统的 JMS MQRFH2 格式的消息的内容。</span><span class="sxs-lookup"><span data-stu-id="5286e-105">These components recognize, validate, and expose metadata and the content of messages that conform to the JMS MQRFH2 format used by IBM MQ Series messaging systems.</span></span> <span data-ttu-id="5286e-106">此功能允许[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]应用程序接收来自消息，并通过 MQ 系列将消息发送到 JMS 系统。</span><span class="sxs-lookup"><span data-stu-id="5286e-106">This functionality allows a [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] application to receive messages from and send messages to JMS systems over MQ Series.</span></span> <span data-ttu-id="5286e-107">组件自动提升到，标头信息，并对其进行降级从消息内容。</span><span class="sxs-lookup"><span data-stu-id="5286e-107">The components automatically promote header information into, and demote it from, the message content.</span></span>  
  
-   <span data-ttu-id="5286e-108">**Namespace 管道组件。**</span><span class="sxs-lookup"><span data-stu-id="5286e-108">**Namespace pipeline components.**</span></span> <span data-ttu-id="5286e-109">这些组件可以添加或删除命名空间中的 XML 消息的内容。</span><span class="sxs-lookup"><span data-stu-id="5286e-109">These components can add or remove namespaces in the content of XML messages.</span></span> <span data-ttu-id="5286e-110">这允许应用程序来修复冲突的命名空间或添加缺少的命名空间，以防止在消息框数据库和应用程序业务流程中的命名空间冲突。</span><span class="sxs-lookup"><span data-stu-id="5286e-110">This allows applications to repair conflicting namespaces or add missing namespaces to prevent namespace collisions within the Message Box database and application orchestrations.</span></span> <span data-ttu-id="5286e-111">组件还允许 BizTalk 服务器而无需修改外部发布系统使用 POX (Plain Old XML)。</span><span class="sxs-lookup"><span data-stu-id="5286e-111">The components also allow BizTalk Server to consume POX (Plain Old XML) without modifying external publishing systems.</span></span>  
  
 <span data-ttu-id="5286e-112">有关 ESB 管道组件的详细信息，请参阅[使用管道支持组件](../esb-toolkit/using-the-pipeline-support-components.md)。</span><span class="sxs-lookup"><span data-stu-id="5286e-112">For more information about the ESB pipeline components, see [Using the Pipeline Support Components](../esb-toolkit/using-the-pipeline-support-components.md).</span></span>