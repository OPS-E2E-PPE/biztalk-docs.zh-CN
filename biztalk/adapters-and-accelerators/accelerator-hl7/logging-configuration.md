---
title: 日志记录配置 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- configuring, auditing
- configuring, logging
- logging, configuring
- auditing, configuring
ms.assetid: 5cd7aec1-bd38-4d37-9a79-b01eeb89337d
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7e90054dc7316cc0fcae2179845ce56c6254f251
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65300034"
---
# <a name="logging-configuration"></a><span data-ttu-id="feb25-102">日志记录配置</span><span class="sxs-lookup"><span data-stu-id="feb25-102">Logging Configuration</span></span>
<span data-ttu-id="feb25-103">在一起，MicrosoftBizTalk 服务器和[!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]提供如医院、 学术会议和护理家庭医疗保健提供商的安全事务和数字企业应用程序集成 (EAI) 通信。</span><span class="sxs-lookup"><span data-stu-id="feb25-103">Together, MicrosoftBizTalk Server and [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] offer secure transactional and digital Enterprise Application Integration (EAI) communications for health care providers such as hospitals, clinics, and nursing homes.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="feb25-104">提供的功能来协调应用程序活动以及事务处理、 动态方式路由消息、 验证和转换数据，并在不同的适配器的传输。</span><span class="sxs-lookup"><span data-stu-id="feb25-104">provides the ability to coordinate application activity and transaction processing, dynamically route messages, validate and transform data, and transport over a variety of adapters.</span></span> [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] <span data-ttu-id="feb25-105">支持美国国家标准标准组织 ANSI 公认运行状况级别 7 (HL7) 消息传送标准，提供程序网络中的临床和管理应用程序用于交换中实时的医疗数据。</span><span class="sxs-lookup"><span data-stu-id="feb25-105">supports the American National Standards Institute (ANSI)-accredited Health Level Seven (HL7) messaging standard used by clinical and administrative applications in provider networks to exchange medical data in real-time.</span></span>  
  
 <span data-ttu-id="feb25-106">通过 accelerator 系统传递的 HL7 消息可以是非常重要。</span><span class="sxs-lookup"><span data-stu-id="feb25-106">The HL7 messages that pass through the accelerator system can be very critical.</span></span> <span data-ttu-id="feb25-107">例如，数据可能是病人的医疗记录或金融交易。</span><span class="sxs-lookup"><span data-stu-id="feb25-107">For example, the data could be a patient's medical record or a financial transaction.</span></span> <span data-ttu-id="feb25-108">若要确保 HL7 安全和隐私法规的符合性，系统管理员必须能够执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="feb25-108">To ensure compliance with HL7 security and privacy regulations, system administrators must be able to do the following:</span></span>  
  
- <span data-ttu-id="feb25-109">调试挂起的消息</span><span class="sxs-lookup"><span data-stu-id="feb25-109">Debug suspended messages</span></span>  
  
- <span data-ttu-id="feb25-110">监视系统和文件访问持续检测潜在的入侵者并减少安全漏洞的威胁的风险</span><span class="sxs-lookup"><span data-stu-id="feb25-110">Monitor system and file access on an ongoing basis to detect potential intruders and reduce the risk of security breaches</span></span>  
  
  <span data-ttu-id="feb25-111">本部分提供可用于配置审核和日志记录、 检查和解释审核数据和事件日志，并对记录的数据运行查询的概念和过程信息。</span><span class="sxs-lookup"><span data-stu-id="feb25-111">This section provides conceptual and procedural information to enable you to configure auditing and logging, examine and interpret audit data and event logs, and run queries against the logged data.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="feb25-112">本节内容</span><span class="sxs-lookup"><span data-stu-id="feb25-112">In This Section</span></span>  
  
-   [<span data-ttu-id="feb25-113">关于日志记录进程</span><span class="sxs-lookup"><span data-stu-id="feb25-113">About the Logging Process</span></span>](../../adapters-and-accelerators/accelerator-hl7/about-the-logging-process.md)  
  
-   [<span data-ttu-id="feb25-114">配置日志记录</span><span class="sxs-lookup"><span data-stu-id="feb25-114">Configuring Logging</span></span>](../../adapters-and-accelerators/accelerator-hl7/configuring-logging.md)