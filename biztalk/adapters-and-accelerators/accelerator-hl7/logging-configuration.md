---
title: "日志记录配置 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- configuring, auditing
- configuring, logging
- logging, configuring
- auditing, configuring
ms.assetid: 5cd7aec1-bd38-4d37-9a79-b01eeb89337d
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 058a1fce8105a3147fb2e537a9182e7d886bb953
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="logging-configuration"></a><span data-ttu-id="125f8-102">日志记录配置</span><span class="sxs-lookup"><span data-stu-id="125f8-102">Logging Configuration</span></span>
<span data-ttu-id="125f8-103">在一起， [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)]和[!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]提供如医院、 诊所和护理家庭卫生保健的提供程序的安全事务性和数字企业应用程序集成 (EAI) 通信。</span><span class="sxs-lookup"><span data-stu-id="125f8-103">Together, [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)] and [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] offer secure transactional and digital Enterprise Application Integration (EAI) communications for health care providers such as hospitals, clinics, and nursing homes.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="125f8-104">提供的功能，以协调应用程序活动和事务处理、 动态将消息路由、 验证和转换数据，并在不同的适配器的传输。</span><span class="sxs-lookup"><span data-stu-id="125f8-104"> provides the ability to coordinate application activity and transaction processing, dynamically route messages, validate and transform data, and transport over a variety of adapters.</span></span> [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="125f8-105">支持美国国家标准标准组织 ANSI 认证运行状况级别七个 (HL7) 消息传递提供程序网络中的临床和管理应用程序用于交换医疗数据进行实时的标准。</span><span class="sxs-lookup"><span data-stu-id="125f8-105"> supports the American National Standards Institute (ANSI)-accredited Health Level Seven (HL7) messaging standard used by clinical and administrative applications in provider networks to exchange medical data in real-time.</span></span>  
  
 <span data-ttu-id="125f8-106">通过此快捷键系统传递 HL7 消息可以是非常关键。</span><span class="sxs-lookup"><span data-stu-id="125f8-106">The HL7 messages that pass through the accelerator system can be very critical.</span></span> <span data-ttu-id="125f8-107">例如，数据可能是一个患者医疗记录或金融交易。</span><span class="sxs-lookup"><span data-stu-id="125f8-107">For example, the data could be a patient's medical record or a financial transaction.</span></span> <span data-ttu-id="125f8-108">若要确保 HL7 安全和隐私法规的合规性，系统管理员必须能够执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="125f8-108">To ensure compliance with HL7 security and privacy regulations, system administrators must be able to do the following:</span></span>  
  
-   <span data-ttu-id="125f8-109">调试挂起的消息</span><span class="sxs-lookup"><span data-stu-id="125f8-109">Debug suspended messages</span></span>  
  
-   <span data-ttu-id="125f8-110">监视不断检测潜在使入侵者和降低安全漏洞的威胁的风险的系统和文件访问</span><span class="sxs-lookup"><span data-stu-id="125f8-110">Monitor system and file access on an ongoing basis to detect potential intruders and reduce the risk of security breaches</span></span>  
  
 <span data-ttu-id="125f8-111">本部分提供概念性和程序性的信息，以使您能够配置审核和日志记录、 检查和解释审核数据和事件日志，并对记录的数据运行查询。</span><span class="sxs-lookup"><span data-stu-id="125f8-111">This section provides conceptual and procedural information to enable you to configure auditing and logging, examine and interpret audit data and event logs, and run queries against the logged data.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="125f8-112">本节内容</span><span class="sxs-lookup"><span data-stu-id="125f8-112">In This Section</span></span>  
  
-   [<span data-ttu-id="125f8-113">有关日志记录流程</span><span class="sxs-lookup"><span data-stu-id="125f8-113">About the Logging Process</span></span>](../../adapters-and-accelerators/accelerator-hl7/about-the-logging-process.md)  
  
-   [<span data-ttu-id="125f8-114">配置日志记录</span><span class="sxs-lookup"><span data-stu-id="125f8-114">Configuring Logging</span></span>](../../adapters-and-accelerators/accelerator-hl7/configuring-logging.md)