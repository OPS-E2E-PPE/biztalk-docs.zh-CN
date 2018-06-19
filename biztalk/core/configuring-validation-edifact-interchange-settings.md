---
title: 配置验证 （EDIFACT 交换设置） |Microsoft 文档
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
ms.openlocfilehash: f87e762177e2938deaa957035e255af3f0d40eab
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22233077"
---
# <a name="configuring-validation-edifact-interchange-settings"></a><span data-ttu-id="d1d9a-102">配置验证（EDIFACT-交换设置）</span><span class="sxs-lookup"><span data-stu-id="d1d9a-102">Configuring Validation (EDIFACT-Interchange Settings)</span></span>
<span data-ttu-id="d1d9a-103">本部分说明如何防止处理重复控制编号。</span><span class="sxs-lookup"><span data-stu-id="d1d9a-103">This section provides instructions on how to prevent duplicate control numbers from being processed.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="d1d9a-104">没有属性禁用此页上，即使你清除**本地 BizTalk 处理接收方或支持从该参与方发送消息的消息**时正在创建你为其创建参与方的复选框协议。</span><span class="sxs-lookup"><span data-stu-id="d1d9a-104">No properties are disabled on this page even if you cleared the **Local BizTalk processes messages received by the party or supports sending messages from this party** check box while creating the party for which you are creating the agreement.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="d1d9a-105">先决条件</span><span class="sxs-lookup"><span data-stu-id="d1d9a-105">Prerequisites</span></span>  
 <span data-ttu-id="d1d9a-106">必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组或 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators 组成员的身份登录。</span><span class="sxs-lookup"><span data-stu-id="d1d9a-106">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-configure-duplicate-validation"></a><span data-ttu-id="d1d9a-107">若要配置重复验证</span><span class="sxs-lookup"><span data-stu-id="d1d9a-107">To configure duplicate validation</span></span>  
  
1.  <span data-ttu-id="d1d9a-108">创建 EDIFACT 编码协议中所述[配置常规设置 (EDIFACT)](../core/configuring-general-settings-edifact.md)。</span><span class="sxs-lookup"><span data-stu-id="d1d9a-108">Create an EDIFACT encoding agreement as described in [Configuring General Settings (EDIFACT)](../core/configuring-general-settings-edifact.md).</span></span> <span data-ttu-id="d1d9a-109">若要更新现有协议，右键单击在协议**方和业务配置文件**页，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="d1d9a-109">To update an existing agreement, right-click the agreement in the **Parties and Business Profiles** page, and click **Properties**.</span></span>  
  
2.  <span data-ttu-id="d1d9a-110">单向协议选项卡上，在**交换设置**部分中，单击**验证**。</span><span class="sxs-lookup"><span data-stu-id="d1d9a-110">On a one-way agreement tab, under **Interchange Settings** section, click **Validation**.</span></span>  
  
3.  <span data-ttu-id="d1d9a-111">选择**交换控制编号 (UNB5)** 复选框以启用接收管道可阻止重复的交换。</span><span class="sxs-lookup"><span data-stu-id="d1d9a-111">Select the **Interchange control number (UNB5)** check box to enable the receive pipeline to block duplicate interchanges.</span></span> <span data-ttu-id="d1d9a-112">如果选中此选项，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 将检查所接收的交换的控制编号是否与接收的其他交换的控制编号匹配。</span><span class="sxs-lookup"><span data-stu-id="d1d9a-112">If selected, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will check that the interchange control number for the received interchange does not match the interchange control number of another received interchange.</span></span> <span data-ttu-id="d1d9a-113">如果检测到匹配，则接收管道将不处理交换。</span><span class="sxs-lookup"><span data-stu-id="d1d9a-113">If a match is detected, the receive pipeline will not process the interchange.</span></span>  
  
4.  <span data-ttu-id="d1d9a-114">如果**交换控制编号 (UNB5)** 选中，则在**检查内重复的 unb5**字段中，输入天数，以检查重复的交换。</span><span class="sxs-lookup"><span data-stu-id="d1d9a-114">If **Interchange control number (UNB5)** is selected, in the **Check for duplicate UNB5 within** field, enter the number of days to check for a duplicate interchange.</span></span>  
  
5.  <span data-ttu-id="d1d9a-115">选择**交换中的组控制编号 (UNG5)** 以防止接收管道处理重复的组。</span><span class="sxs-lookup"><span data-stu-id="d1d9a-115">Select **Group control number (UNG5) in interchange** to prevent the receive pipeline from processing duplicate groups.</span></span>  
  
6.  <span data-ttu-id="d1d9a-116">选择**事务集控制编号 (UNH1) 组中**以防止接收管道处理重复的事务设置。</span><span class="sxs-lookup"><span data-stu-id="d1d9a-116">Select **Transaction Set Control Number (UNH1) in group** to prevent the receive pipeline from processing duplicate transaction sets.</span></span>  
  
7.  <span data-ttu-id="d1d9a-117">单击**应用**接受所做的更改，然后才能继续进行配置，或单击**确定**验证所做的更改，然后关闭对话框。</span><span class="sxs-lookup"><span data-stu-id="d1d9a-117">Click **Apply** to accept the changes before continuing with the configuration, or click **OK** to validate the changes and then close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1d9a-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d1d9a-118">See Also</span></span>  
 [<span data-ttu-id="d1d9a-119">配置交换设置 (EDIFACT)</span><span class="sxs-lookup"><span data-stu-id="d1d9a-119">Configuring Interchange Settings (EDIFACT)</span></span>](../core/configuring-interchange-settings-edifact.md)