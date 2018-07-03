---
title: 步骤 7： 创建示例 LOB 消息 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, LOB
- loopback tutorial, creating LOB message
- creating, LOB messages
- LOBs, creating messages
ms.assetid: 3023bbc0-5bc4-4e5a-a345-c3253874f0d3
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d2b8450f196a1619b55b08a0771508daafa421a4
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36977998"
---
# <a name="step-7-create-a-sample-lob-message"></a><span data-ttu-id="1cf44-102">步骤 7： 创建示例 LOB 消息</span><span class="sxs-lookup"><span data-stu-id="1cf44-102">Step 7: Create a Sample LOB Message</span></span>
<span data-ttu-id="1cf44-103">在此步骤中，你将使用 LOB 应用程序实用工具创建一个业务线 (LOB) 消息示例。</span><span class="sxs-lookup"><span data-stu-id="1cf44-103">In this step, you use the LOB Application utility to create a sample line-of-business (LOB) message.</span></span>  

### <a name="to-create-a-sample-message-using-the-lob-application-utility"></a><span data-ttu-id="1cf44-104">使用 LOB 应用程序实用工具创建示例消息</span><span class="sxs-lookup"><span data-stu-id="1cf44-104">To create a sample message using the LOB Application utility</span></span>  

1. <span data-ttu-id="1cf44-105">在中[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]资源管理器，转到\<*驱动器*\>: \Program 文件 (x86) \Microsoft BizTalk\<版本\>Accelerator for RosettaNet\SDK 文件夹，然后双击**LOBApplication.exe**。</span><span class="sxs-lookup"><span data-stu-id="1cf44-105">In [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Explorer, move to \<*drive*\>:\Program Files (x86)\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK folder, and then double-click **LOBApplication.exe**.</span></span>  

2. <span data-ttu-id="1cf44-106">在中**LOB 应用程序**对话框框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="1cf44-106">In the **LOB Application** dialog box, do the following:</span></span>  


   |       <span data-ttu-id="1cf44-107">**使用此**</span><span class="sxs-lookup"><span data-stu-id="1cf44-107">**Use this**</span></span>       |                                                                                                                       <span data-ttu-id="1cf44-108">**若要执行此操作**</span><span class="sxs-lookup"><span data-stu-id="1cf44-108">**To do this**</span></span>                                                                                                                       |
   |--------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |  <span data-ttu-id="1cf44-109">**本组织配置文件名称**</span><span class="sxs-lookup"><span data-stu-id="1cf44-109">**Home Profile Name**</span></span>   |                                                                                                                       <span data-ttu-id="1cf44-110">类型**主页**。</span><span class="sxs-lookup"><span data-stu-id="1cf44-110">Type **HOME**.</span></span>                                                                                                                       |
   | <span data-ttu-id="1cf44-111">**贸易合作伙伴名称**</span><span class="sxs-lookup"><span data-stu-id="1cf44-111">**Trading Partner Name**</span></span> |                                                                                                                     <span data-ttu-id="1cf44-112">类型**合作伙伴**。</span><span class="sxs-lookup"><span data-stu-id="1cf44-112">Type **PARTNER**.</span></span>                                                                                                                      |
   |       <span data-ttu-id="1cf44-113">**PIP 名称**</span><span class="sxs-lookup"><span data-stu-id="1cf44-113">**PIP Name**</span></span>       |                                                                                                                       <span data-ttu-id="1cf44-114">类型**0c1**。</span><span class="sxs-lookup"><span data-stu-id="1cf44-114">Type **0C1**.</span></span>                                                                                                                        |
   |     <span data-ttu-id="1cf44-115">**PIP 版本**</span><span class="sxs-lookup"><span data-stu-id="1cf44-115">**PIP Version**</span></span>      |                                                                                                                      <span data-ttu-id="1cf44-116">类型**R01.02**。</span><span class="sxs-lookup"><span data-stu-id="1cf44-116">Type **R01.02**.</span></span>                                                                                                                      |
   |      <span data-ttu-id="1cf44-117">**文件名**</span><span class="sxs-lookup"><span data-stu-id="1cf44-117">**File Name**</span></span>       | <span data-ttu-id="1cf44-118">单击省略号按钮 (**...**)，并将移至\<*驱动器*:\>\Program 文件 (x86) \Microsoft BizTalk\<版本\>Accelerator for RosettaNet\SDK\LOBApplication\SampleInstances.</span><span class="sxs-lookup"><span data-stu-id="1cf44-118">Click the ellipsis button (**...**), and move to \<*drive*:\>\Program Files (x86)\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\LOBApplication\SampleInstances.</span></span> <span data-ttu-id="1cf44-119">选择**0C1_Request.xml**从列表中的文件，并单击**打开**。</span><span class="sxs-lookup"><span data-stu-id="1cf44-119">Select **0C1_Request.xml** from the list of files, and then click **Open**.</span></span> |
   |   <span data-ttu-id="1cf44-120">**消息类别**</span><span class="sxs-lookup"><span data-stu-id="1cf44-120">**Message Category**</span></span>   |                                                                                                         <span data-ttu-id="1cf44-121">选择**操作**从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="1cf44-121">Select **Action** from the drop-down list.</span></span>                                                                                                         |


3. <span data-ttu-id="1cf44-122">在中**LOB 应用程序**对话框中，单击**提交消息**。</span><span class="sxs-lookup"><span data-stu-id="1cf44-122">In the **LOB Application** dialog box, click **Submit Message**.</span></span>  

   <span data-ttu-id="1cf44-123">LOB 应用程序为 Microsoft 生成一条消息[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]模拟的 LOB 应用程序生成的原始消息。</span><span class="sxs-lookup"><span data-stu-id="1cf44-123">The LOB application generates a message for Microsoft [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] simulating an original message generated by an LOB application.</span></span> <span data-ttu-id="1cf44-124">可以在“状态”窗口中查看消息的状态。</span><span class="sxs-lookup"><span data-stu-id="1cf44-124">You can view the status of the message in the Status window.</span></span>  

> [!NOTE]
>  <span data-ttu-id="1cf44-125">该消息示例假设“HOME”和“PARTNER”的全局业务标识符 (GBI) 分别为 123456789 和 987654321。</span><span class="sxs-lookup"><span data-stu-id="1cf44-125">The sample messages assume that the Global Business Identifiers (GBI) for "HOME" and "PARTNER" are 123456789 and 987654321, respectively.</span></span> <span data-ttu-id="1cf44-126">若要使用不同的 GBI，必须修改这些文件的内容。</span><span class="sxs-lookup"><span data-stu-id="1cf44-126">To use a different GBI, you must modify the content of these files.</span></span>  

## <a name="see-also"></a><span data-ttu-id="1cf44-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="1cf44-127">See Also</span></span>  
 [<span data-ttu-id="1cf44-128">步骤 8：在 BTARN 数据库中查看消息</span><span class="sxs-lookup"><span data-stu-id="1cf44-128">Step 8: View Messages in the BTARN Databases</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-8-view-messages-in-the-btarn-databases.md)
