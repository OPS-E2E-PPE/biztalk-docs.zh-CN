---
title: 操作日志记录、 消息批处理、 验证和确认设置 |Microsoft Docs
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
ms.openlocfilehash: 015182a6b091ccbba7452df4c44ed4e4f45c336e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36974678"
---
# <a name="operational-logging-message-batching-validation-and-asknowledgment-settings"></a><span data-ttu-id="80e67-102">操作日志记录、 消息批处理、 验证和确认设置</span><span class="sxs-lookup"><span data-stu-id="80e67-102">Operational logging, message batching, validation and asknowledgment settings</span></span>
<span data-ttu-id="80e67-103">Microsoft[!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)]包含服务器和系列的工具，用于企业应用程序集成 (EAI) 自动执行业务流程，促进与业务合作伙伴之间的交互。</span><span class="sxs-lookup"><span data-stu-id="80e67-103">Microsoft [!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)] encompasses a server and series of tools for enterprise application integration (EAI), automating business processes, and facilitating interactions with business partners.</span></span> <span data-ttu-id="80e67-104">基于[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]平台，BTAHL7 将升级的任何工具使用 HL7 标准的医疗应用程序集成。</span><span class="sxs-lookup"><span data-stu-id="80e67-104">Built on the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] platform, BTAHL7 promotes medical application integration for any facility using the HL7 standard.</span></span> <span data-ttu-id="80e67-105">HL7 包含标准的交换、 集成和检索电子临床做法和管理信息。</span><span class="sxs-lookup"><span data-stu-id="80e67-105">HL7 contains standards for exchanging, integrating, and retrieving electronic information in clinical practice and management.</span></span>  
  
 <span data-ttu-id="80e67-106">接口用户分析师配置贸易合作伙伴、 消息确认、 消息批处理，和业务过程所需的其他详细信息。</span><span class="sxs-lookup"><span data-stu-id="80e67-106">Interface user analysts configure trading partners, message acknowledgments, message batching, and other details that your business process requires.</span></span>  
  
 <span data-ttu-id="80e67-107">本部分提供使您能够有效地监视和维护您 BTAHL7 的应用程序环境的概念和过程信息。</span><span class="sxs-lookup"><span data-stu-id="80e67-107">This section provides conceptual and procedural information that enables you to effectively monitor and maintain your BTAHL7 application environment.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="80e67-108">本节内容</span><span class="sxs-lookup"><span data-stu-id="80e67-108">In This Section</span></span>  
  
-   [<span data-ttu-id="80e67-109">日志记录配置</span><span class="sxs-lookup"><span data-stu-id="80e67-109">Logging Configuration</span></span>](../../adapters-and-accelerators/accelerator-hl7/logging-configuration.md)  
  
-   [<span data-ttu-id="80e67-110">消息批处理</span><span class="sxs-lookup"><span data-stu-id="80e67-110">Message Batching</span></span>](../../adapters-and-accelerators/accelerator-hl7/message-batching.md)  
  
-   [<span data-ttu-id="80e67-111">验证设置</span><span class="sxs-lookup"><span data-stu-id="80e67-111">Validation Settings</span></span>](../../adapters-and-accelerators/accelerator-hl7/validation-settings.md)  
  
-   [<span data-ttu-id="80e67-112">MSH 字段替代</span><span class="sxs-lookup"><span data-stu-id="80e67-112">MSH Field Overrides</span></span>](../../adapters-and-accelerators/accelerator-hl7/msh-field-overrides.md)  
  
-   [<span data-ttu-id="80e67-113">确认设置</span><span class="sxs-lookup"><span data-stu-id="80e67-113">Acknowledgment Settings</span></span>](../../adapters-and-accelerators/accelerator-hl7/acknowledgment-settings.md)  
  
-   [<span data-ttu-id="80e67-114">扩展的编码支持</span><span class="sxs-lookup"><span data-stu-id="80e67-114">Extended Encoding Support</span></span>](../../adapters-and-accelerators/accelerator-hl7/extended-encoding-support.md)