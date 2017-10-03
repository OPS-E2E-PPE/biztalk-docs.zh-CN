---
title: "配置回退验证属性 (EDIFACT) |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b925d063-e24b-4cfb-acbd-dcadb511011d
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bf0e103eb2e20bb64973cd207ed2a55c2f91e58d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-fallback-validation-properties-edifact"></a><span data-ttu-id="3e3c5-102">配置回退验证属性 (EDIFACT)</span><span class="sxs-lookup"><span data-stu-id="3e3c5-102">Configuring Fallback Validation Properties (EDIFACT)</span></span>
<span data-ttu-id="3e3c5-103">本部分说明如何防止处理重复控制编号。</span><span class="sxs-lookup"><span data-stu-id="3e3c5-103">This section provides instructions on how to prevent duplicate control numbers from being processed.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="3e3c5-104">先决条件</span><span class="sxs-lookup"><span data-stu-id="3e3c5-104">Prerequisites</span></span>  
 <span data-ttu-id="3e3c5-105">必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组或 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators 组成员的身份登录。</span><span class="sxs-lookup"><span data-stu-id="3e3c5-105">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-configure-duplicate-validation"></a><span data-ttu-id="3e3c5-106">若要配置重复验证</span><span class="sxs-lookup"><span data-stu-id="3e3c5-106">To configure duplicate validation</span></span>  
  
1.  <span data-ttu-id="3e3c5-107">在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**方**节点，，然后单击**EDIFACT 回退设置**。</span><span class="sxs-lookup"><span data-stu-id="3e3c5-107">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, right-click the **Parties** node, and then click **EDIFACT Fallback Settings**.</span></span>  
  
2.  <span data-ttu-id="3e3c5-108">在**EDIFACT 回退设置**对话框中，在**EDIFACT 协议页**选项卡上，在**交换设置**部分中，单击**验证**.</span><span class="sxs-lookup"><span data-stu-id="3e3c5-108">In the **EDIFACT Fallback Settings** dialog box, in the **EDIFACT Agreement Pages** tab, under the **Interchange Settings** section, click **Validation**.</span></span>  
  
3.  <span data-ttu-id="3e3c5-109">选择**交换控制编号 (UNB5)**复选框以启用接收管道可阻止重复的交换。</span><span class="sxs-lookup"><span data-stu-id="3e3c5-109">Select the **Interchange control number (UNB5)** check box to enable the receive pipeline to block duplicate interchanges.</span></span> <span data-ttu-id="3e3c5-110">如果选中此选项，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 将检查所接收的交换的控制编号是否与接收的其他交换的控制编号匹配。</span><span class="sxs-lookup"><span data-stu-id="3e3c5-110">If selected, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will check that the interchange control number for the received interchange does not match the interchange control number of another received interchange.</span></span> <span data-ttu-id="3e3c5-111">如果检测到匹配，则接收管道将不处理交换。</span><span class="sxs-lookup"><span data-stu-id="3e3c5-111">If a match is detected, the receive pipeline will not process the interchange.</span></span>  
  
4.  <span data-ttu-id="3e3c5-112">如果**交换控制编号 (UNB5)**选中，则在**检查内重复的 unb5**字段中，输入天数，以检查重复的交换。</span><span class="sxs-lookup"><span data-stu-id="3e3c5-112">If **Interchange control number (UNB5)** is selected, in the **Check for duplicate UNB5 within** field, enter the number of days to check for a duplicate interchange.</span></span>  
  
5.  <span data-ttu-id="3e3c5-113">选择**交换中的组控制编号 (UNG5)**以防止接收管道处理重复的组。</span><span class="sxs-lookup"><span data-stu-id="3e3c5-113">Select **Group control number (UNG5) in interchange** to prevent the receive pipeline from processing duplicate groups.</span></span>  
  
6.  <span data-ttu-id="3e3c5-114">选择**事务集控制编号 (UNH1) 组中**以防止接收管道处理重复的事务设置。</span><span class="sxs-lookup"><span data-stu-id="3e3c5-114">Select **Transaction Set Control Number (UNH1) in group** to prevent the receive pipeline from processing duplicate transaction sets.</span></span>  
  
7.  <span data-ttu-id="3e3c5-115">单击**应用**接受所做的更改，然后才能继续进行配置，或单击**确定**验证所做的更改，然后关闭对话框。</span><span class="sxs-lookup"><span data-stu-id="3e3c5-115">Click **Apply** to accept the changes before continuing with the configuration, or click **OK** to validate the changes and then close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e3c5-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3e3c5-116">See Also</span></span>  
 [<span data-ttu-id="3e3c5-117">为交换处理配置 EDIFACT 回退协议属性</span><span class="sxs-lookup"><span data-stu-id="3e3c5-117">Configuring EDIFACT Fallback Agreement Properties for Interchange Processing</span></span>](../core/configuring-edifact-fallback-agreement-properties-for-interchange-processing.md)