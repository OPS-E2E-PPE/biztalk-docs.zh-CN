---
title: ESB 管道互操作组件 |Microsoft Docs
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
ms.openlocfilehash: 1dc0693ca97928b4b5977a9969da667423d13ce1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65306102"
---
# <a name="esb-pipeline-interop-components"></a><span data-ttu-id="0f7cb-102">ESB 管道互操作组件</span><span class="sxs-lookup"><span data-stu-id="0f7cb-102">ESB Pipeline Interop Components</span></span>
<span data-ttu-id="0f7cb-103">[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]提供支持组件和服务，包括以下：</span><span class="sxs-lookup"><span data-stu-id="0f7cb-103">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] provides support components and services, including the following:</span></span>  
  
- <span data-ttu-id="0f7cb-104">**JMS 管道组件。**</span><span class="sxs-lookup"><span data-stu-id="0f7cb-104">**JMS pipeline components.**</span></span> <span data-ttu-id="0f7cb-105">这些组件识别、 验证和公开元数据和遵守使用 IBM MQ Series 的消息传递系统的 JMS MQRFH2 格式的消息的内容。</span><span class="sxs-lookup"><span data-stu-id="0f7cb-105">These components recognize, validate, and expose metadata and the content of messages that conform to the JMS MQRFH2 format used by IBM MQ Series messaging systems.</span></span> <span data-ttu-id="0f7cb-106">此功能允许[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]应用程序接收消息并通过 MQ Series 将消息发送到 JMS 系统。</span><span class="sxs-lookup"><span data-stu-id="0f7cb-106">This functionality allows a [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] application to receive messages from and send messages to JMS systems over MQ Series.</span></span> <span data-ttu-id="0f7cb-107">组件会自动将提升到，标头信息和从消息内容对其进行降级。</span><span class="sxs-lookup"><span data-stu-id="0f7cb-107">The components automatically promote header information into, and demote it from, the message content.</span></span>  
  
- <span data-ttu-id="0f7cb-108">**Namespace 管道组件。**</span><span class="sxs-lookup"><span data-stu-id="0f7cb-108">**Namespace pipeline components.**</span></span> <span data-ttu-id="0f7cb-109">这些组件可以添加或删除命名空间中的 XML 消息的内容。</span><span class="sxs-lookup"><span data-stu-id="0f7cb-109">These components can add or remove namespaces in the content of XML messages.</span></span> <span data-ttu-id="0f7cb-110">这样，应用程序来修复冲突的命名空间或添加缺少的命名空间以避免在 Messagebox 数据库和应用程序业务流程中的命名空间冲突。</span><span class="sxs-lookup"><span data-stu-id="0f7cb-110">This allows applications to repair conflicting namespaces or add missing namespaces to prevent namespace collisions within the Message Box database and application orchestrations.</span></span> <span data-ttu-id="0f7cb-111">组件还允许 BizTalk Server 使用 POX (Plain Old XML)，而无需修改外部发布系统。</span><span class="sxs-lookup"><span data-stu-id="0f7cb-111">The components also allow BizTalk Server to consume POX (Plain Old XML) without modifying external publishing systems.</span></span>  
  
  <span data-ttu-id="0f7cb-112">ESB 管道组件的详细信息，请参阅[使用管道支持组件](../esb-toolkit/using-the-pipeline-support-components.md)。</span><span class="sxs-lookup"><span data-stu-id="0f7cb-112">For more information about the ESB pipeline components, see [Using the Pipeline Support Components](../esb-toolkit/using-the-pipeline-support-components.md).</span></span>