---
title: 配置验证 （EDIFACT-交换设置） |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 55820ebc-fe21-48a3-8985-1bf4184176ac
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5999d52c8896a750810edfa64c0874c8d0948fef
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65355033"
---
# <a name="configuring-validation-edifact-interchange-settings"></a><span data-ttu-id="0f242-102">配置验证 （EDIFACT-交换设置）</span><span class="sxs-lookup"><span data-stu-id="0f242-102">Configuring Validation (EDIFACT-Interchange Settings)</span></span>
<span data-ttu-id="0f242-103">本部分将说明了如何防止处理重复控制编号。</span><span class="sxs-lookup"><span data-stu-id="0f242-103">This section provides instructions on how to prevent duplicate control numbers from being processed.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="0f242-104">没有属性禁用此页上，即使您清除**本地 BizTalk 处理参与方或支持来自此参与方发送消息的接收的消息**要为其创建的参与方时的复选框协议。</span><span class="sxs-lookup"><span data-stu-id="0f242-104">No properties are disabled on this page even if you cleared the **Local BizTalk processes messages received by the party or supports sending messages from this party** check box while creating the party for which you are creating the agreement.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="0f242-105">先决条件</span><span class="sxs-lookup"><span data-stu-id="0f242-105">Prerequisites</span></span>  
 <span data-ttu-id="0f242-106">必须以成员的身份登录[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理员或[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]B2B Operators 组。</span><span class="sxs-lookup"><span data-stu-id="0f242-106">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-configure-duplicate-validation"></a><span data-ttu-id="0f242-107">若要配置重复验证</span><span class="sxs-lookup"><span data-stu-id="0f242-107">To configure duplicate validation</span></span>  
  
1. <span data-ttu-id="0f242-108">创建 EDIFACT 编码协议，如中所述[配置常规设置 (EDIFACT)](../core/configuring-general-settings-edifact.md)。</span><span class="sxs-lookup"><span data-stu-id="0f242-108">Create an EDIFACT encoding agreement as described in [Configuring General Settings (EDIFACT)](../core/configuring-general-settings-edifact.md).</span></span> <span data-ttu-id="0f242-109">若要更新现有的协议，请右键单击中的协议**参与方和业务配置文件**页，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="0f242-109">To update an existing agreement, right-click the agreement in the **Parties and Business Profiles** page, and click **Properties**.</span></span>  
  
2. <span data-ttu-id="0f242-110">在单向协议选项卡下**交换设置**部分中，单击**验证**。</span><span class="sxs-lookup"><span data-stu-id="0f242-110">On a one-way agreement tab, under **Interchange Settings** section, click **Validation**.</span></span>  
  
3. <span data-ttu-id="0f242-111">选择**交换控制编号 (UNB5)** 复选框以启用接收管道可阻止重复交换。</span><span class="sxs-lookup"><span data-stu-id="0f242-111">Select the **Interchange control number (UNB5)** check box to enable the receive pipeline to block duplicate interchanges.</span></span> <span data-ttu-id="0f242-112">如果选择，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将检查接收交换的交换控制编号与接收的其他交换的交换控制编号不匹配。</span><span class="sxs-lookup"><span data-stu-id="0f242-112">If selected, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will check that the interchange control number for the received interchange does not match the interchange control number of another received interchange.</span></span> <span data-ttu-id="0f242-113">如果检测到匹配项，则接收管道将不处理交换。</span><span class="sxs-lookup"><span data-stu-id="0f242-113">If a match is detected, the receive pipeline will not process the interchange.</span></span>  
  
4. <span data-ttu-id="0f242-114">如果**交换控制编号 (UNB5)** 处于选中状态，在**检查重复的 UNB5 范围**字段中，输入天数，以检查是否有重复交换。</span><span class="sxs-lookup"><span data-stu-id="0f242-114">If **Interchange control number (UNB5)** is selected, in the **Check for duplicate UNB5 within** field, enter the number of days to check for a duplicate interchange.</span></span>  
  
5. <span data-ttu-id="0f242-115">选择**交换中的组控制编号 (UNG5)** 以阻止接收管道处理重复的组。</span><span class="sxs-lookup"><span data-stu-id="0f242-115">Select **Group control number (UNG5) in interchange** to prevent the receive pipeline from processing duplicate groups.</span></span>  
  
6. <span data-ttu-id="0f242-116">选择**事务集控制编号 (UNH1) 组中**以阻止接收管道处理重复的事务设置。</span><span class="sxs-lookup"><span data-stu-id="0f242-116">Select **Transaction Set Control Number (UNH1) in group** to prevent the receive pipeline from processing duplicate transaction sets.</span></span>  
  
7. <span data-ttu-id="0f242-117">单击**Apply**以接受更改，然后才能继续进行配置，或单击**确定**以验证所做的更改，然后关闭对话框。</span><span class="sxs-lookup"><span data-stu-id="0f242-117">Click **Apply** to accept the changes before continuing with the configuration, or click **OK** to validate the changes and then close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f242-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="0f242-118">See Also</span></span>  
 [<span data-ttu-id="0f242-119">配置交换设置 (EDIFACT)</span><span class="sxs-lookup"><span data-stu-id="0f242-119">Configuring Interchange Settings (EDIFACT)</span></span>](../core/configuring-interchange-settings-edifact.md)