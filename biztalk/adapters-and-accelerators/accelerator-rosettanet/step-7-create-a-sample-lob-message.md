---
title: 步骤 7：创建示例 LOB 消息 |Microsoft Docs
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
ms.openlocfilehash: c39df356056e8f8f5f9bcf7d136eda302003096e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65280616"
---
# <a name="step-7-create-a-sample-lob-message"></a><span data-ttu-id="faafd-102">步骤 7：创建示例 LOB 消息</span><span class="sxs-lookup"><span data-stu-id="faafd-102">Step 7: Create a Sample LOB Message</span></span>
<span data-ttu-id="faafd-103">在此步骤中，使用 LOB 应用程序实用工具创建示例业务 (LOB) 消息。</span><span class="sxs-lookup"><span data-stu-id="faafd-103">In this step, you use the LOB Application utility to create a sample line-of-business (LOB) message.</span></span>  

### <a name="to-create-a-sample-message-using-the-lob-application-utility"></a><span data-ttu-id="faafd-104">若要创建使用 LOB 应用程序实用工具的示例消息</span><span class="sxs-lookup"><span data-stu-id="faafd-104">To create a sample message using the LOB Application utility</span></span>  

1. <span data-ttu-id="faafd-105">在中[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]资源管理器，转到\<*驱动器*\>: \Program 文件 (x86) \Microsoft BizTalk\<版本\>Accelerator for RosettaNet\SDK 文件夹，然后双击**LOBApplication.exe**。</span><span class="sxs-lookup"><span data-stu-id="faafd-105">In [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Explorer, move to \<*drive*\>:\Program Files (x86)\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK folder, and then double-click **LOBApplication.exe**.</span></span>  

2. <span data-ttu-id="faafd-106">在中**LOB 应用程序**对话框框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="faafd-106">In the **LOB Application** dialog box, do the following:</span></span>  


   |       <span data-ttu-id="faafd-107">**使用此**</span><span class="sxs-lookup"><span data-stu-id="faafd-107">**Use this**</span></span>       |                                                                                                                       <span data-ttu-id="faafd-108">**若要执行此操作**</span><span class="sxs-lookup"><span data-stu-id="faafd-108">**To do this**</span></span>                                                                                                                       |
   |--------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |  <span data-ttu-id="faafd-109">**本组织配置文件名称**</span><span class="sxs-lookup"><span data-stu-id="faafd-109">**Home Profile Name**</span></span>   |                                                                                                                       <span data-ttu-id="faafd-110">类型**主页**。</span><span class="sxs-lookup"><span data-stu-id="faafd-110">Type **HOME**.</span></span>                                                                                                                       |
   | <span data-ttu-id="faafd-111">**贸易合作伙伴名称**</span><span class="sxs-lookup"><span data-stu-id="faafd-111">**Trading Partner Name**</span></span> |                                                                                                                     <span data-ttu-id="faafd-112">类型**合作伙伴**。</span><span class="sxs-lookup"><span data-stu-id="faafd-112">Type **PARTNER**.</span></span>                                                                                                                      |
   |       <span data-ttu-id="faafd-113">**PIP 名称**</span><span class="sxs-lookup"><span data-stu-id="faafd-113">**PIP Name**</span></span>       |                                                                                                                       <span data-ttu-id="faafd-114">类型**0c1**。</span><span class="sxs-lookup"><span data-stu-id="faafd-114">Type **0C1**.</span></span>                                                                                                                        |
   |     <span data-ttu-id="faafd-115">**PIP 版本**</span><span class="sxs-lookup"><span data-stu-id="faafd-115">**PIP Version**</span></span>      |                                                                                                                      <span data-ttu-id="faafd-116">类型**R01.02**。</span><span class="sxs-lookup"><span data-stu-id="faafd-116">Type **R01.02**.</span></span>                                                                                                                      |
   |      <span data-ttu-id="faafd-117">**文件名**</span><span class="sxs-lookup"><span data-stu-id="faafd-117">**File Name**</span></span>       | <span data-ttu-id="faafd-118">单击省略号按钮 (**...**)，并将移至\<*驱动器*:\>\Program 文件 (x86) \Microsoft BizTalk\<版本\>Accelerator for RosettaNet\SDK\LOBApplication\SampleInstances.</span><span class="sxs-lookup"><span data-stu-id="faafd-118">Click the ellipsis button (**...**), and move to \<*drive*:\>\Program Files (x86)\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\LOBApplication\SampleInstances.</span></span> <span data-ttu-id="faafd-119">选择**0C1_Request.xml**从列表中的文件，并单击**打开**。</span><span class="sxs-lookup"><span data-stu-id="faafd-119">Select **0C1_Request.xml** from the list of files, and then click **Open**.</span></span> |
   |   <span data-ttu-id="faafd-120">**消息类别**</span><span class="sxs-lookup"><span data-stu-id="faafd-120">**Message Category**</span></span>   |                                                                                                         <span data-ttu-id="faafd-121">选择**操作**从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="faafd-121">Select **Action** from the drop-down list.</span></span>                                                                                                         |


3. <span data-ttu-id="faafd-122">在中**LOB 应用程序**对话框中，单击**提交消息**。</span><span class="sxs-lookup"><span data-stu-id="faafd-122">In the **LOB Application** dialog box, click **Submit Message**.</span></span>  

   <span data-ttu-id="faafd-123">LOB 应用程序为 Microsoft 生成一条消息[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]模拟的 LOB 应用程序生成的原始消息。</span><span class="sxs-lookup"><span data-stu-id="faafd-123">The LOB application generates a message for Microsoft [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] simulating an original message generated by an LOB application.</span></span> <span data-ttu-id="faafd-124">可以在状态窗口中查看消息的状态。</span><span class="sxs-lookup"><span data-stu-id="faafd-124">You can view the status of the message in the Status window.</span></span>  

> [!NOTE]
>  <span data-ttu-id="faafd-125">该消息示例假设"HOME"的全局业务标识符 (GBI) 和"合作伙伴"是为 123456789 和 987654321 分别。</span><span class="sxs-lookup"><span data-stu-id="faafd-125">The sample messages assume that the Global Business Identifiers (GBI) for "HOME" and "PARTNER" are 123456789 and 987654321, respectively.</span></span> <span data-ttu-id="faafd-126">若要使用不同的 GBI，必须修改这些文件的内容。</span><span class="sxs-lookup"><span data-stu-id="faafd-126">To use a different GBI, you must modify the content of these files.</span></span>  

## <a name="see-also"></a><span data-ttu-id="faafd-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="faafd-127">See Also</span></span>  
 [<span data-ttu-id="faafd-128">步骤 8：在 BTARN 数据库中查看消息</span><span class="sxs-lookup"><span data-stu-id="faafd-128">Step 8: View Messages in the BTARN Databases</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-8-view-messages-in-the-btarn-databases.md)
