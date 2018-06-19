---
title: 配置验证 （X12 交换设置） |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fdad7016-1d66-4d11-b620-c28368f00133
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0edfe66791fa5c041c66a3adddde61730afe54ad
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22233269"
---
# <a name="configuring-validation-x12-interchange-settings"></a><span data-ttu-id="fa6d1-102">配置验证（X 12 交换设置）</span><span class="sxs-lookup"><span data-stu-id="fa6d1-102">Configuring Validation (X12-Interchange Settings)</span></span>
<span data-ttu-id="fa6d1-103">X12 交换验证生成设置定义 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 如何检查收到的交换中重复的控制编号。</span><span class="sxs-lookup"><span data-stu-id="fa6d1-103">X12 interchange validation generation settings define how [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] checks for duplicate control numbers in the received interchange.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fa6d1-104">此处所述的设置也适用于 HIPAA 交换验证。</span><span class="sxs-lookup"><span data-stu-id="fa6d1-104">The settings described here also apply to HIPAA interchange validation.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="fa6d1-105">没有属性禁用此页上，即使你清除**本地 BizTalk 处理接收方或支持从该参与方发送消息的消息**时正在创建你为其创建参与方的复选框协议。</span><span class="sxs-lookup"><span data-stu-id="fa6d1-105">No properties are disabled on this page even if you cleared the **Local BizTalk processes messages received by the party or supports sending messages from this party** check box while creating the party for which you are creating the agreement.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="fa6d1-106">先决条件</span><span class="sxs-lookup"><span data-stu-id="fa6d1-106">Prerequisites</span></span>  
 <span data-ttu-id="fa6d1-107">必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组或 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators 组成员的身份登录。</span><span class="sxs-lookup"><span data-stu-id="fa6d1-107">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-configure-validation"></a><span data-ttu-id="fa6d1-108">若要配置验证</span><span class="sxs-lookup"><span data-stu-id="fa6d1-108">To configure validation</span></span>  
  
1.  <span data-ttu-id="fa6d1-109">创建 X12 编码协议中所述[配置常规设置 (X12)](../core/configuring-general-settings-x12.md)。</span><span class="sxs-lookup"><span data-stu-id="fa6d1-109">Create an X12 encoding agreement as described in [Configuring General Settings (X12)](../core/configuring-general-settings-x12.md).</span></span> <span data-ttu-id="fa6d1-110">若要更新现有协议，右键单击在协议**方和业务配置文件**页，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="fa6d1-110">To update an existing agreement, right-click the agreement in the **Parties and Business Profiles** page, and click **Properties**.</span></span>  
  
2.  <span data-ttu-id="fa6d1-111">单向协议选项卡上，在**交换设置**部分中，单击**验证**。</span><span class="sxs-lookup"><span data-stu-id="fa6d1-111">On a one-way agreement tab, under **Interchange Settings** section, click **Validation**.</span></span>  
  
3.  <span data-ttu-id="fa6d1-112">选择**交换控制编号**复选框以启用接收管道可阻止重复的交换。</span><span class="sxs-lookup"><span data-stu-id="fa6d1-112">Select the **Interchange Control Number** check box to enable the receive pipeline to block duplicate interchanges.</span></span> <span data-ttu-id="fa6d1-113">如果选中此选项，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 将检查所接收交换的交换控制编号 (ISA13) 是否与交换控制编号匹配。</span><span class="sxs-lookup"><span data-stu-id="fa6d1-113">If selected, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will check that the interchange control number (ISA13) for the received interchange does not match the interchange control number.</span></span> <span data-ttu-id="fa6d1-114">如果检测到匹配，则接收管道将不处理交换。</span><span class="sxs-lookup"><span data-stu-id="fa6d1-114">If a match is detected, the receive pipeline will not process the interchange.</span></span>  
  
4.  <span data-ttu-id="fa6d1-115">如果**交换控制编号**选中，则在**检查内重复的 isa13**字段中，输入将使用特定执行的检查重复的交换的天数交换控制编号。</span><span class="sxs-lookup"><span data-stu-id="fa6d1-115">If **Interchange Control Number** is selected, in the **Check for duplicate ISA13 within** field, enter the number of days that a check for a duplicate interchange will be performed using a specific interchange control number.</span></span>  
  
5.  <span data-ttu-id="fa6d1-116">选择**组控制编号**以防止接收管道处理具有重复组控制编号 (GS6) 的交换。</span><span class="sxs-lookup"><span data-stu-id="fa6d1-116">Select **Group Control Number** to prevent the receive pipeline from processing interchanges with duplicate group control numbers (GS6).</span></span>  
  
6.  <span data-ttu-id="fa6d1-117">选择**事务集控制编号**以防止接收管道处理具有重复事务集控制编号 (ST2) 的交换。</span><span class="sxs-lookup"><span data-stu-id="fa6d1-117">Select **Transaction Set Control Number** to prevent the receive pipeline from processing interchanges with duplicate transaction set control numbers (ST2).</span></span>  
  
7.  <span data-ttu-id="fa6d1-118">单击**应用**接受所做的更改，然后才能继续进行配置，或单击**确定**验证所做的更改，然后关闭对话框。</span><span class="sxs-lookup"><span data-stu-id="fa6d1-118">Click **Apply** to accept the changes before continuing with the configuration, or click **OK** to validate the changes and then close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa6d1-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fa6d1-119">See Also</span></span>  
 [<span data-ttu-id="fa6d1-120">配置交换设置 (X12)</span><span class="sxs-lookup"><span data-stu-id="fa6d1-120">Configuring Interchange Settings (X12)</span></span>](../core/configuring-interchange-settings-x12.md)