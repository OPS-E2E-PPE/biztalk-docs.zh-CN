---
title: 批处理定义选项卡 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- btahl7.configurationexplorer.tab.batchdefinition
helpviewer_keywords:
- Batch Definition tab [Configuration Explorer]
- batching, configuring
- configuring, batching
ms.assetid: fe8685ef-5de5-4337-8691-8e4094056ace
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 70d06bb7832d42264d90d0edd63faf5d747bf849
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65247672"
---
# <a name="batch-definition-tab"></a><span data-ttu-id="a955e-102">批处理定义选项卡</span><span class="sxs-lookup"><span data-stu-id="a955e-102">Batch Definition Tab</span></span>
<span data-ttu-id="a955e-103">您使用**批定义**选项卡以启用中的入站批处理，批处理 / 出站批处理，批处理并选择可用架构以供出站批处理。</span><span class="sxs-lookup"><span data-stu-id="a955e-103">You use the **Batch Definition** tab to enable inbound batching, batch in/batch out batching, and select available schemas for outbound batching.</span></span>  

 <span data-ttu-id="a955e-104">在中**BTAHL7 配置资源管理器**对话框中，在**批定义**选项卡上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="a955e-104">In the **BTAHL7 Configuration Explorer** dialog box, on the **Batch Definition** tab, do the following:</span></span>  


|                   <span data-ttu-id="a955e-105">使用此选项</span><span class="sxs-lookup"><span data-stu-id="a955e-105">Use this</span></span>                   |                                                                                                                                                            <span data-ttu-id="a955e-106">执行的操作</span><span class="sxs-lookup"><span data-stu-id="a955e-106">To do this</span></span>                                                                                                                                                            |
|----------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|          <span data-ttu-id="a955e-107">**所需的碎片**</span><span class="sxs-lookup"><span data-stu-id="a955e-107">**Fragmentation required**</span></span>          |                                                           <span data-ttu-id="a955e-108">选择以下选项之一：</span><span class="sxs-lookup"><span data-stu-id="a955e-108">Select one of the following options:</span></span><br /><br /> <span data-ttu-id="a955e-109">-   **是**。</span><span class="sxs-lookup"><span data-stu-id="a955e-109">-   **Yes**.</span></span> <span data-ttu-id="a955e-110">若要启用碎片。</span><span class="sxs-lookup"><span data-stu-id="a955e-110">To enable fragmentation.</span></span><br /><span data-ttu-id="a955e-111">-   **不**。</span><span class="sxs-lookup"><span data-stu-id="a955e-111">-   **No**.</span></span> <span data-ttu-id="a955e-112">若要禁用碎片。</span><span class="sxs-lookup"><span data-stu-id="a955e-112">To disable fragmentation.</span></span> <span data-ttu-id="a955e-113">**注意：** 对于新的参与方，**所需的碎片**默认值为**否**。</span><span class="sxs-lookup"><span data-stu-id="a955e-113">**Note:**  For a new party, **Fragmentation Required** defaults to **No**.</span></span>                                                           |
| <span data-ttu-id="a955e-114">**所需的可恢复的交换支持**</span><span class="sxs-lookup"><span data-stu-id="a955e-114">**Recoverable interchange support required**</span></span> | <span data-ttu-id="a955e-115">选择以下选项之一：</span><span class="sxs-lookup"><span data-stu-id="a955e-115">Select one of the following options:</span></span><br /><br /> <span data-ttu-id="a955e-116">-   **True**。</span><span class="sxs-lookup"><span data-stu-id="a955e-116">-   **True**.</span></span> <span data-ttu-id="a955e-117">若要启用可恢复的交换的支持。</span><span class="sxs-lookup"><span data-stu-id="a955e-117">To enable recoverable interchange support.</span></span><br /><span data-ttu-id="a955e-118">-   **FALSE**。</span><span class="sxs-lookup"><span data-stu-id="a955e-118">-   **FALSE**.</span></span> <span data-ttu-id="a955e-119">若要禁用可恢复的交换的支持。</span><span class="sxs-lookup"><span data-stu-id="a955e-119">To disable recoverable interchange support.</span></span> <span data-ttu-id="a955e-120">**注意：** 对于新的参与方，**所需的碎片**默认值为**FALSE**才会启用和的值**所需的碎片**是**否**。</span><span class="sxs-lookup"><span data-stu-id="a955e-120">**Note:**  For a new party, **Fragmentation Required** defaults to **FALSE** and is enabled only if the value of **Fragmentation Required** is **No**.</span></span> |
|             <span data-ttu-id="a955e-121">**选择消息**</span><span class="sxs-lookup"><span data-stu-id="a955e-121">**Select Messages**</span></span>              |                              <span data-ttu-id="a955e-122">选择你想要从可用消息窗口中作为一个批发送，然后单击向右箭头移动的消息类型 (**>>**)。</span><span class="sxs-lookup"><span data-stu-id="a955e-122">Select the message types you want to send as a batch from the Available Messages window and then click the Move to right arrow (**>>**).</span></span><br /><br /> <span data-ttu-id="a955e-123">若要传入的确认消息进行批处理，必须添加 ACK 消息类型。</span><span class="sxs-lookup"><span data-stu-id="a955e-123">To batch incoming ACK messages, you must add the ACK message type.</span></span> <span data-ttu-id="a955e-124">您为此部署的 ACK 消息架构。</span><span class="sxs-lookup"><span data-stu-id="a955e-124">You do so by deploying the ACK message schema.</span></span>                              |
|      <span data-ttu-id="a955e-125">**选择消息确认**</span><span class="sxs-lookup"><span data-stu-id="a955e-125">**Select Message Acknowledgments**</span></span>      |                               <span data-ttu-id="a955e-126">选择为其所需的消息类型[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]从可用的消息确认窗口中，作为批处理发送确认，然后单击向右箭头 (**>>**)。</span><span class="sxs-lookup"><span data-stu-id="a955e-126">Select the message types for which you want [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] to send the acknowledgments as a batch from the Available Message Acks window, and then click the Move to right arrow (**>>**).</span></span>                                |

