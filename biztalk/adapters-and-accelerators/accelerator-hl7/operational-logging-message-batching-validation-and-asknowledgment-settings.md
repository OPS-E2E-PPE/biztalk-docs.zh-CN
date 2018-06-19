---
title: 操作日志记录、 消息批处理、 验证和 asknowledgment 设置 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BTAHL7, administering
- managing
- BTAHL7, managing
- administering
ms.assetid: c7376de4-4e1d-47e2-acf7-0a32e7a4b073
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b3282d69fc572c4aa32888f9a3ed8a806deef5c8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22205997"
---
# <a name="operational-logging-message-batching-validation-and-asknowledgment-settings"></a><span data-ttu-id="954a4-102">操作日志记录、 消息批处理、 验证和 asknowledgment 设置</span><span class="sxs-lookup"><span data-stu-id="954a4-102">Operational logging, message batching, validation and asknowledgment settings</span></span>
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]<span data-ttu-id="954a4-103">[!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)]包含服务器和系列的工具，为企业应用程序集成 (EAI)，自动执行业务流程和促进与业务合作伙伴之间的交互。</span><span class="sxs-lookup"><span data-stu-id="954a4-103"> [!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)] encompasses a server and series of tools for enterprise application integration (EAI), automating business processes, and facilitating interactions with business partners.</span></span> <span data-ttu-id="954a4-104">基于[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]平台，BTAHL7 提升使用 HL7 标准任何设施的医疗应用程序集成。</span><span class="sxs-lookup"><span data-stu-id="954a4-104">Built on the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] platform, BTAHL7 promotes medical application integration for any facility using the HL7 standard.</span></span> <span data-ttu-id="954a4-105">HL7 包含标准交换、 集成和检索电子中临床实践及其管理的信息。</span><span class="sxs-lookup"><span data-stu-id="954a4-105">HL7 contains standards for exchanging, integrating, and retrieving electronic information in clinical practice and management.</span></span>  
  
 <span data-ttu-id="954a4-106">接口用户分析师配置贸易合作伙伴、 消息确认、 消息进行批处理，和你的业务过程需要的其他详细信息。</span><span class="sxs-lookup"><span data-stu-id="954a4-106">Interface user analysts configure trading partners, message acknowledgments, message batching, and other details that your business process requires.</span></span>  
  
 <span data-ttu-id="954a4-107">本部分提供概念性和程序性使您能够有效地监视和维护 BTAHL7 应用程序环境的信息。</span><span class="sxs-lookup"><span data-stu-id="954a4-107">This section provides conceptual and procedural information that enables you to effectively monitor and maintain your BTAHL7 application environment.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="954a4-108">本节内容</span><span class="sxs-lookup"><span data-stu-id="954a4-108">In This Section</span></span>  
  
-   [<span data-ttu-id="954a4-109">日志记录配置</span><span class="sxs-lookup"><span data-stu-id="954a4-109">Logging Configuration</span></span>](../../adapters-and-accelerators/accelerator-hl7/logging-configuration.md)  
  
-   [<span data-ttu-id="954a4-110">消息批处理</span><span class="sxs-lookup"><span data-stu-id="954a4-110">Message Batching</span></span>](../../adapters-and-accelerators/accelerator-hl7/message-batching.md)  
  
-   [<span data-ttu-id="954a4-111">验证设置</span><span class="sxs-lookup"><span data-stu-id="954a4-111">Validation Settings</span></span>](../../adapters-and-accelerators/accelerator-hl7/validation-settings.md)  
  
-   [<span data-ttu-id="954a4-112">MSH 字段将覆盖</span><span class="sxs-lookup"><span data-stu-id="954a4-112">MSH Field Overrides</span></span>](../../adapters-and-accelerators/accelerator-hl7/msh-field-overrides.md)  
  
-   [<span data-ttu-id="954a4-113">确认设置</span><span class="sxs-lookup"><span data-stu-id="954a4-113">Acknowledgment Settings</span></span>](../../adapters-and-accelerators/accelerator-hl7/acknowledgment-settings.md)  
  
-   [<span data-ttu-id="954a4-114">扩展编码的支持</span><span class="sxs-lookup"><span data-stu-id="954a4-114">Extended Encoding Support</span></span>](../../adapters-and-accelerators/accelerator-hl7/extended-encoding-support.md)