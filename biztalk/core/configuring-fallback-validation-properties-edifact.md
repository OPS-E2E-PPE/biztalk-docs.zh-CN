---
title: 配置回退验证属性 (EDIFACT) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b925d063-e24b-4cfb-acbd-dcadb511011d
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4276ad1b5ae995cfb6370377d7d1671ede09bd52
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36975446"
---
# <a name="configuring-fallback-validation-properties-edifact"></a><span data-ttu-id="c37bf-102">配置回退验证属性 (EDIFACT)</span><span class="sxs-lookup"><span data-stu-id="c37bf-102">Configuring Fallback Validation Properties (EDIFACT)</span></span>
<span data-ttu-id="c37bf-103">本部分说明如何防止处理重复控制编号。</span><span class="sxs-lookup"><span data-stu-id="c37bf-103">This section provides instructions on how to prevent duplicate control numbers from being processed.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="c37bf-104">必要條件</span><span class="sxs-lookup"><span data-stu-id="c37bf-104">Prerequisites</span></span>  
 <span data-ttu-id="c37bf-105">必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组或 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators 组成员的身份登录。</span><span class="sxs-lookup"><span data-stu-id="c37bf-105">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-configure-duplicate-validation"></a><span data-ttu-id="c37bf-106">若要配置重复验证</span><span class="sxs-lookup"><span data-stu-id="c37bf-106">To configure duplicate validation</span></span>  
  
1. <span data-ttu-id="c37bf-107">在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**方**节点，，然后单击**EDIFACT 后备设置**。</span><span class="sxs-lookup"><span data-stu-id="c37bf-107">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, right-click the **Parties** node, and then click **EDIFACT Fallback Settings**.</span></span>  
  
2. <span data-ttu-id="c37bf-108">在中**EDIFACT 后备设置**对话框中**EDIFACT 协议页**选项卡上，在**交换设置**部分中，单击**验证**.</span><span class="sxs-lookup"><span data-stu-id="c37bf-108">In the **EDIFACT Fallback Settings** dialog box, in the **EDIFACT Agreement Pages** tab, under the **Interchange Settings** section, click **Validation**.</span></span>  
  
3. <span data-ttu-id="c37bf-109">选择**交换控制编号 (UNB5)** 复选框以启用接收管道可阻止重复交换。</span><span class="sxs-lookup"><span data-stu-id="c37bf-109">Select the **Interchange control number (UNB5)** check box to enable the receive pipeline to block duplicate interchanges.</span></span> <span data-ttu-id="c37bf-110">如果选中此选项，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 将检查所接收的交换的控制编号是否与接收的其他交换的控制编号匹配。</span><span class="sxs-lookup"><span data-stu-id="c37bf-110">If selected, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will check that the interchange control number for the received interchange does not match the interchange control number of another received interchange.</span></span> <span data-ttu-id="c37bf-111">如果检测到匹配，则接收管道将不处理交换。</span><span class="sxs-lookup"><span data-stu-id="c37bf-111">If a match is detected, the receive pipeline will not process the interchange.</span></span>  
  
4. <span data-ttu-id="c37bf-112">如果**交换控制编号 (UNB5)** 处于选中状态，在**检查重复的 UNB5 范围**字段中，输入天数，以检查是否有重复交换。</span><span class="sxs-lookup"><span data-stu-id="c37bf-112">If **Interchange control number (UNB5)** is selected, in the **Check for duplicate UNB5 within** field, enter the number of days to check for a duplicate interchange.</span></span>  
  
5. <span data-ttu-id="c37bf-113">选择**交换中的组控制编号 (UNG5)** 以阻止接收管道处理重复的组。</span><span class="sxs-lookup"><span data-stu-id="c37bf-113">Select **Group control number (UNG5) in interchange** to prevent the receive pipeline from processing duplicate groups.</span></span>  
  
6. <span data-ttu-id="c37bf-114">选择**事务集控制编号 (UNH1) 组中**以阻止接收管道处理重复的事务设置。</span><span class="sxs-lookup"><span data-stu-id="c37bf-114">Select **Transaction Set Control Number (UNH1) in group** to prevent the receive pipeline from processing duplicate transaction sets.</span></span>  
  
7. <span data-ttu-id="c37bf-115">单击**Apply**以接受更改，然后才能继续进行配置，或单击**确定**以验证所做的更改，然后关闭对话框。</span><span class="sxs-lookup"><span data-stu-id="c37bf-115">Click **Apply** to accept the changes before continuing with the configuration, or click **OK** to validate the changes and then close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c37bf-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="c37bf-116">See Also</span></span>  
 [<span data-ttu-id="c37bf-117">为交换处理配置 EDIFACT 后备协议属性</span><span class="sxs-lookup"><span data-stu-id="c37bf-117">Configuring EDIFACT Fallback Agreement Properties for Interchange Processing</span></span>](../core/configuring-edifact-fallback-agreement-properties-for-interchange-processing.md)