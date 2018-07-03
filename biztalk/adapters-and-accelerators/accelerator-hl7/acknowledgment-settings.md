---
title: 确认设置 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- acknowledgements, configuring
- acknowledgements, acknowledgement types
- configuring, acknowledgements
ms.assetid: 99ab8caa-8788-4438-96db-8001a6523cc8
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f8c1f19fa1a0d1abaad29f454f25f0d8608ed497
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36967134"
---
# <a name="acknowledgment-settings"></a><span data-ttu-id="c4c3d-102">确认设置</span><span class="sxs-lookup"><span data-stu-id="c4c3d-102">Acknowledgment Settings</span></span>
<span data-ttu-id="c4c3d-103">您使用**确认**选项卡[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]配置资源管理器 (在高级下**方**选项卡) 配置确认 (ACK) 设置。</span><span class="sxs-lookup"><span data-stu-id="c4c3d-103">You use the **Acknowledgment** tab of [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Configuration Explorer (under the high-level **Parties** tab) to configure acknowledgment (ACK) settings.</span></span>  
  
 <span data-ttu-id="c4c3d-104">下面的确认类型可用于：</span><span class="sxs-lookup"><span data-stu-id="c4c3d-104">The following acknowledgment types are available:</span></span>  
  
- <span data-ttu-id="c4c3d-105">**无**。</span><span class="sxs-lookup"><span data-stu-id="c4c3d-105">**None**.</span></span> <span data-ttu-id="c4c3d-106">如果不想配置任何确认，请选择此选项。</span><span class="sxs-lookup"><span data-stu-id="c4c3d-106">Select this option if you do not want to configure any acknowledgments.</span></span>  
  
- <span data-ttu-id="c4c3d-107">**原始**。</span><span class="sxs-lookup"><span data-stu-id="c4c3d-107">**Original**.</span></span> <span data-ttu-id="c4c3d-108">选择此选项以配置**MSH1 – 字段分隔符**， **MSH2 – 编码的字符**，并**MSH8 – 安全**仅选项。</span><span class="sxs-lookup"><span data-stu-id="c4c3d-108">Select this option to configure **MSH1 – Field Separator**, **MSH2 – Encoding Characters**, and the **MSH8 – Security** options only.</span></span>  
  
- <span data-ttu-id="c4c3d-109">**增强型**。</span><span class="sxs-lookup"><span data-stu-id="c4c3d-109">**Enhanced**.</span></span> <span data-ttu-id="c4c3d-110">选择此选项以配置所有可用确认选项。</span><span class="sxs-lookup"><span data-stu-id="c4c3d-110">Select this option to configure all available acknowledgment options.</span></span>  
  
- <span data-ttu-id="c4c3d-111">**延迟**。</span><span class="sxs-lookup"><span data-stu-id="c4c3d-111">**Deferred**.</span></span> <span data-ttu-id="c4c3d-112">选择此选项以配置**MSH1 – 字段分隔符**， **MSH2 – 编码的字符**，并**MSH8 – 安全**仅选项。</span><span class="sxs-lookup"><span data-stu-id="c4c3d-112">Select this option to configure **MSH1 – Field Separator**, **MSH2 – Encoding Characters**, and **MSH8 – Security** options only.</span></span>  
  
- <span data-ttu-id="c4c3d-113">**静态**。</span><span class="sxs-lookup"><span data-stu-id="c4c3d-113">**Static**.</span></span> <span data-ttu-id="c4c3d-114">选择此选项以配置**成功**并**失败**确认选项。</span><span class="sxs-lookup"><span data-stu-id="c4c3d-114">Select this option to configure the **On success** and **On failure** acknowledgment options.</span></span>  
  
  <span data-ttu-id="c4c3d-115">确认类型设置后，可以设置标头字段和确认，的值取决于的确认类型。</span><span class="sxs-lookup"><span data-stu-id="c4c3d-115">Once the acknowledgment type is set, you can set values for header fields and acknowledgments, depending upon the acknowledgment type.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c4c3d-116">本节内容</span><span class="sxs-lookup"><span data-stu-id="c4c3d-116">In This Section</span></span>  
  
-   [<span data-ttu-id="c4c3d-117">ACK 配置设置</span><span class="sxs-lookup"><span data-stu-id="c4c3d-117">ACK Configuration Settings</span></span>](../../adapters-and-accelerators/accelerator-hl7/ack-configuration-settings.md)  
  
-   [<span data-ttu-id="c4c3d-118">配置消息确认</span><span class="sxs-lookup"><span data-stu-id="c4c3d-118">Configuring Message Acknowledgments</span></span>](../../adapters-and-accelerators/accelerator-hl7/configuring-message-acknowledgments.md)