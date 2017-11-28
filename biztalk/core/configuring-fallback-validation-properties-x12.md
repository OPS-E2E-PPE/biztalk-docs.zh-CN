---
title: "配置回退验证属性 (X12) |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1a64431d-373a-4d63-9b83-cbb323620152
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fc6eb44f2ee4c2f9c63011dc14be41380c245996
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-fallback-validation-properties-x12"></a><span data-ttu-id="2eafb-102">配置回退验证属性 (X 12)</span><span class="sxs-lookup"><span data-stu-id="2eafb-102">Configuring Fallback Validation Properties (X12)</span></span>
<span data-ttu-id="2eafb-103">X12 交换验证生成后备设置定义 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 如何检查收到的交换中重复的控制编号。</span><span class="sxs-lookup"><span data-stu-id="2eafb-103">X12 interchange validation generation fallback settings define how [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] checks for duplicate control numbers in the received interchange.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2eafb-104">此处所述的设置也适用于 HIPAA 交换验证。</span><span class="sxs-lookup"><span data-stu-id="2eafb-104">The settings described here also apply to HIPAA interchange validation.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="2eafb-105">先决条件</span><span class="sxs-lookup"><span data-stu-id="2eafb-105">Prerequisites</span></span>  
 <span data-ttu-id="2eafb-106">必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组或 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators 组成员的身份登录。</span><span class="sxs-lookup"><span data-stu-id="2eafb-106">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-configure-validation"></a><span data-ttu-id="2eafb-107">若要配置验证</span><span class="sxs-lookup"><span data-stu-id="2eafb-107">To configure validation</span></span>  
  
1.  <span data-ttu-id="2eafb-108">在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**方**节点，，然后单击**X12 回退设置**。</span><span class="sxs-lookup"><span data-stu-id="2eafb-108">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, right-click the **Parties** node, and then click **X12 Fallback Settings**.</span></span>  
  
2.  <span data-ttu-id="2eafb-109">在**X12 回退设置**对话框中，在**X12 协议页**选项卡上，在**交换设置**部分中，单击**验证**.</span><span class="sxs-lookup"><span data-stu-id="2eafb-109">In the **X12 Fallback Settings** dialog box, in the **X12 Agreement Pages** tab, under the **Interchange Settings** section, click **Validation**.</span></span>  
  
3.  <span data-ttu-id="2eafb-110">选择**交换控制编号**复选框以启用接收管道可阻止重复的交换。</span><span class="sxs-lookup"><span data-stu-id="2eafb-110">Select the **Interchange Control Number** check box to enable the receive pipeline to block duplicate interchanges.</span></span> <span data-ttu-id="2eafb-111">如果选中此选项，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 将检查所接收交换的交换控制编号 (ISA13) 是否与交换控制编号匹配。</span><span class="sxs-lookup"><span data-stu-id="2eafb-111">If selected, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will check that the interchange control number (ISA13) for the received interchange does not match the interchange control number.</span></span> <span data-ttu-id="2eafb-112">如果检测到匹配，则接收管道将不处理交换。</span><span class="sxs-lookup"><span data-stu-id="2eafb-112">If a match is detected, the receive pipeline will not process the interchange.</span></span>  
  
4.  <span data-ttu-id="2eafb-113">如果**交换控制编号**选中，则在**检查内重复的 isa13**字段中，输入将使用特定执行的检查重复的交换的天数交换控制编号。</span><span class="sxs-lookup"><span data-stu-id="2eafb-113">If **Interchange Control Number** is selected, in the **Check for duplicate ISA13 within** field, enter the number of days that a check for a duplicate interchange will be performed using a specific interchange control number.</span></span>  
  
5.  <span data-ttu-id="2eafb-114">选择**组控制编号**以防止接收管道处理具有重复组控制编号 (GS6) 的交换。</span><span class="sxs-lookup"><span data-stu-id="2eafb-114">Select **Group Control Number** to prevent the receive pipeline from processing interchanges with duplicate group control numbers (GS6).</span></span>  
  
6.  <span data-ttu-id="2eafb-115">选择**事务集控制编号**以防止接收管道处理具有重复事务集控制编号 (ST2) 的交换。</span><span class="sxs-lookup"><span data-stu-id="2eafb-115">Select **Transaction Set Control Number** to prevent the receive pipeline from processing interchanges with duplicate transaction set control numbers (ST2).</span></span>  
  
7.  <span data-ttu-id="2eafb-116">单击**应用**接受所做的更改，然后才能继续进行配置，或单击**确定**验证所做的更改，然后关闭对话框。</span><span class="sxs-lookup"><span data-stu-id="2eafb-116">Click **Apply** to accept the changes before continuing with the configuration, or click **OK** to validate the changes and then close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2eafb-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2eafb-117">See Also</span></span>  
 [<span data-ttu-id="2eafb-118">配置 X12 回退协议属性交换处理</span><span class="sxs-lookup"><span data-stu-id="2eafb-118">Configuring X12 Fallback Agreement Properties for Interchange Processing</span></span>](../core/configuring-x12-fallback-agreement-properties-for-interchange-processing.md)