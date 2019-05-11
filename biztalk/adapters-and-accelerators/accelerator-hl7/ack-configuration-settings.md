---
title: ACK 配置设置 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- acknowledgements, configuring
- configuring, acknowledgements
ms.assetid: 46e92560-7b1e-4d53-9de8-8ded4de90695
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f75a9ded38c45f71c16b011087eff3b90b740b8e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65247528"
---
# <a name="ack-configuration-settings"></a><span data-ttu-id="3e7fb-102">ACK 配置设置</span><span class="sxs-lookup"><span data-stu-id="3e7fb-102">ACK Configuration Settings</span></span>
<span data-ttu-id="3e7fb-103">Microsoft[!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]分析器生成确认基于贸易合作伙伴管理 (TPM) 设置。</span><span class="sxs-lookup"><span data-stu-id="3e7fb-103">The Microsoft [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] parser generates acknowledgments based on Trading Partner Management (TPM) settings.</span></span> <span data-ttu-id="3e7fb-104">确认 (ACK) 设置都依赖于合作伙伴信息。</span><span class="sxs-lookup"><span data-stu-id="3e7fb-104">The acknowledgment (ACK) settings are dependent on partner information.</span></span> <span data-ttu-id="3e7fb-105">不使用架构类型。</span><span class="sxs-lookup"><span data-stu-id="3e7fb-105">Schema type is not used.</span></span> <span data-ttu-id="3e7fb-106">当[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]与 MSH15 字段含有 AL、 SU 或 ER，接收到 ACK 消息[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]可能会发送此信息基于分析的 ACK 标头和 TPM 配置的结果的 ACK。</span><span class="sxs-lookup"><span data-stu-id="3e7fb-106">When [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] receives an ACK message with the MSH15 field containing AL, SU or ER, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] may send an ACK for this message based on the result of parsing the ACK header and TPM configuration.</span></span> [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] <span data-ttu-id="3e7fb-107">检索合作伙伴确认设置并返回以下五个值之一：</span><span class="sxs-lookup"><span data-stu-id="3e7fb-107">retrieves the partner ACK settings and returns one of the following five values:</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3e7fb-108">HL7 规范也要求使用项 1 至 4，并且用于填充您生成的 ACK 消息 MSH15 字段。</span><span class="sxs-lookup"><span data-stu-id="3e7fb-108">The HL7 specification mandates that you use items 1 through 4 and to populate the MSH15 field of an ACK message that you generate.</span></span> <span data-ttu-id="3e7fb-109">第 5 项是[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]的特定表示不能生成确认。</span><span class="sxs-lookup"><span data-stu-id="3e7fb-109">Item 5 is [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]-specific and denotes not to generate an ACK.</span></span>  
  
1.  <span data-ttu-id="3e7fb-110">AL – 始终</span><span class="sxs-lookup"><span data-stu-id="3e7fb-110">AL – Always</span></span>  
  
2.  <span data-ttu-id="3e7fb-111">NE – 永远不会</span><span class="sxs-lookup"><span data-stu-id="3e7fb-111">NE – Never</span></span>  
  
3.  <span data-ttu-id="3e7fb-112">SU-成功</span><span class="sxs-lookup"><span data-stu-id="3e7fb-112">SU – Success</span></span>  
  
4.  <span data-ttu-id="3e7fb-113">ER-错误</span><span class="sxs-lookup"><span data-stu-id="3e7fb-113">ER – Error</span></span>  
  
5.  <span data-ttu-id="3e7fb-114">否-不会生成确认</span><span class="sxs-lookup"><span data-stu-id="3e7fb-114">NO – Do not generate an ACK</span></span>  
  
## <a name="ack-configuration-inconsistency"></a><span data-ttu-id="3e7fb-115">ACK 配置不一致问题</span><span class="sxs-lookup"><span data-stu-id="3e7fb-115">ACK configuration inconsistency</span></span>  
 <span data-ttu-id="3e7fb-116">在确认配置用户界面设置和消息实例 MSH15 和 MSH16 字段内的值之间的不一致的情况下[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]时的两个 ACK 生成触发器之一需要发送确认。</span><span class="sxs-lookup"><span data-stu-id="3e7fb-116">In the case of inconsistency between the ACK configuration user interface settings and values inside the message instance MSH15 and MSH16 fields, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] sends an ACK when one of the two ACK generation triggers require it.</span></span> <span data-ttu-id="3e7fb-117">对于其他不一致，实例中的数据将覆盖在配置用户界面中的设置。</span><span class="sxs-lookup"><span data-stu-id="3e7fb-117">In the case of other inconsistencies, the data in the instance will override the setting in the configuration user interface.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e7fb-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="3e7fb-118">See Also</span></span>  
 <span data-ttu-id="3e7fb-119">[配置消息确认](../../adapters-and-accelerators/accelerator-hl7/configuring-message-acknowledgments.md) </span><span class="sxs-lookup"><span data-stu-id="3e7fb-119">[Configuring Message Acknowledgments](../../adapters-and-accelerators/accelerator-hl7/configuring-message-acknowledgments.md) </span></span>  
 [<span data-ttu-id="3e7fb-120">创建和处理确认</span><span class="sxs-lookup"><span data-stu-id="3e7fb-120">Creating and Processing Acknowledgments</span></span>](../../adapters-and-accelerators/accelerator-hl7/creating-and-processing-acknowledgments.md)