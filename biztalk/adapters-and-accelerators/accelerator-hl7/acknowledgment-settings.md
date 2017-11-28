---
title: "确认设置 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- acknowledgements, configuring
- acknowledgements, acknowledgement types
- configuring, acknowledgements
ms.assetid: 99ab8caa-8788-4438-96db-8001a6523cc8
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 34eda8a977de0dadbad974268b46e4d580cc1f33
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="acknowledgment-settings"></a><span data-ttu-id="f6468-102">确认设置</span><span class="sxs-lookup"><span data-stu-id="f6468-102">Acknowledgment Settings</span></span>
<span data-ttu-id="f6468-103">你使用**确认**选项卡[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]配置资源管理器 (在高级下**方**选项卡) 配置确认 (ACK) 设置。</span><span class="sxs-lookup"><span data-stu-id="f6468-103">You use the **Acknowledgment** tab of [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Configuration Explorer (under the high-level **Parties** tab) to configure acknowledgment (ACK) settings.</span></span>  
  
 <span data-ttu-id="f6468-104">以下的确认类型有：</span><span class="sxs-lookup"><span data-stu-id="f6468-104">The following acknowledgment types are available:</span></span>  
  
-   <span data-ttu-id="f6468-105">**无**。</span><span class="sxs-lookup"><span data-stu-id="f6468-105">**None**.</span></span> <span data-ttu-id="f6468-106">如果你不想要配置任何确认，请选择此选项。</span><span class="sxs-lookup"><span data-stu-id="f6468-106">Select this option if you do not want to configure any acknowledgments.</span></span>  
  
-   <span data-ttu-id="f6468-107">**原始**。</span><span class="sxs-lookup"><span data-stu-id="f6468-107">**Original**.</span></span> <span data-ttu-id="f6468-108">选择此选项以配置**MSH1 – 字段分隔符**， **MSH2 – 编码的字符**，和**MSH8 – 安全**仅选项。</span><span class="sxs-lookup"><span data-stu-id="f6468-108">Select this option to configure **MSH1 – Field Separator**, **MSH2 – Encoding Characters**, and the **MSH8 – Security** options only.</span></span>  
  
-   <span data-ttu-id="f6468-109">**增强**。</span><span class="sxs-lookup"><span data-stu-id="f6468-109">**Enhanced**.</span></span> <span data-ttu-id="f6468-110">选择此选项以配置所有可用确认选项。</span><span class="sxs-lookup"><span data-stu-id="f6468-110">Select this option to configure all available acknowledgment options.</span></span>  
  
-   <span data-ttu-id="f6468-111">**延迟**。</span><span class="sxs-lookup"><span data-stu-id="f6468-111">**Deferred**.</span></span> <span data-ttu-id="f6468-112">选择此选项以配置**MSH1 – 字段分隔符**， **MSH2 – 编码的字符**，和**MSH8 – 安全**仅选项。</span><span class="sxs-lookup"><span data-stu-id="f6468-112">Select this option to configure **MSH1 – Field Separator**, **MSH2 – Encoding Characters**, and **MSH8 – Security** options only.</span></span>  
  
-   <span data-ttu-id="f6468-113">**静态**。</span><span class="sxs-lookup"><span data-stu-id="f6468-113">**Static**.</span></span> <span data-ttu-id="f6468-114">选择此选项以配置**成功**和**失败**确认选项。</span><span class="sxs-lookup"><span data-stu-id="f6468-114">Select this option to configure the **On success** and **On failure** acknowledgment options.</span></span>  
  
 <span data-ttu-id="f6468-115">设置的确认类型后，可以设置标头字段和确认，的值取决于的确认类型。</span><span class="sxs-lookup"><span data-stu-id="f6468-115">Once the acknowledgment type is set, you can set values for header fields and acknowledgments, depending upon the acknowledgment type.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f6468-116">本节内容</span><span class="sxs-lookup"><span data-stu-id="f6468-116">In This Section</span></span>  
  
-   [<span data-ttu-id="f6468-117">ACK 配置设置</span><span class="sxs-lookup"><span data-stu-id="f6468-117">ACK Configuration Settings</span></span>](../../adapters-and-accelerators/accelerator-hl7/ack-configuration-settings.md)  
  
-   [<span data-ttu-id="f6468-118">配置消息确认</span><span class="sxs-lookup"><span data-stu-id="f6468-118">Configuring Message Acknowledgments</span></span>](../../adapters-and-accelerators/accelerator-hl7/configuring-message-acknowledgments.md)