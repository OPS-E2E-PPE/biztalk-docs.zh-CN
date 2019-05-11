---
title: 配置验证 （X12-交换设置） |Microsoft Docs
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
ms.openlocfilehash: 0782546e8d016aba2f8ccc4bcd5b7ad5e81412de
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65355087"
---
# <a name="configuring-validation-x12-interchange-settings"></a><span data-ttu-id="026ee-102">配置验证（X 12 交换设置）</span><span class="sxs-lookup"><span data-stu-id="026ee-102">Configuring Validation (X12-Interchange Settings)</span></span>
<span data-ttu-id="026ee-103">X12 交换验证生成设置定义如何[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]检查收到的交换中的重复控制编号。</span><span class="sxs-lookup"><span data-stu-id="026ee-103">X12 interchange validation generation settings define how [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] checks for duplicate control numbers in the received interchange.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="026ee-104">此处所述的设置也适用于 HIPAA 交换验证。</span><span class="sxs-lookup"><span data-stu-id="026ee-104">The settings described here also apply to HIPAA interchange validation.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="026ee-105">没有属性禁用此页上，即使您清除**本地 BizTalk 处理参与方或支持来自此参与方发送消息的接收的消息**要为其创建的参与方时的复选框协议。</span><span class="sxs-lookup"><span data-stu-id="026ee-105">No properties are disabled on this page even if you cleared the **Local BizTalk processes messages received by the party or supports sending messages from this party** check box while creating the party for which you are creating the agreement.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="026ee-106">先决条件</span><span class="sxs-lookup"><span data-stu-id="026ee-106">Prerequisites</span></span>  
 <span data-ttu-id="026ee-107">必须以成员的身份登录[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理员或[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]B2B Operators 组。</span><span class="sxs-lookup"><span data-stu-id="026ee-107">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-configure-validation"></a><span data-ttu-id="026ee-108">若要配置验证</span><span class="sxs-lookup"><span data-stu-id="026ee-108">To configure validation</span></span>  
  
1. <span data-ttu-id="026ee-109">创建 X12 编码协议，如中所述[配置常规设置 (X12)](../core/configuring-general-settings-x12.md)。</span><span class="sxs-lookup"><span data-stu-id="026ee-109">Create an X12 encoding agreement as described in [Configuring General Settings (X12)](../core/configuring-general-settings-x12.md).</span></span> <span data-ttu-id="026ee-110">若要更新现有的协议，请右键单击中的协议**参与方和业务配置文件**页，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="026ee-110">To update an existing agreement, right-click the agreement in the **Parties and Business Profiles** page, and click **Properties**.</span></span>  
  
2. <span data-ttu-id="026ee-111">在单向协议选项卡下**交换设置**部分中，单击**验证**。</span><span class="sxs-lookup"><span data-stu-id="026ee-111">On a one-way agreement tab, under **Interchange Settings** section, click **Validation**.</span></span>  
  
3. <span data-ttu-id="026ee-112">选择**交换控制编号**复选框以启用接收管道可阻止重复交换。</span><span class="sxs-lookup"><span data-stu-id="026ee-112">Select the **Interchange Control Number** check box to enable the receive pipeline to block duplicate interchanges.</span></span> <span data-ttu-id="026ee-113">如果选择，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]会检查收到的交换的交换控制编号 (ISA13) 与交换控制编号不匹配。</span><span class="sxs-lookup"><span data-stu-id="026ee-113">If selected, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will check that the interchange control number (ISA13) for the received interchange does not match the interchange control number.</span></span> <span data-ttu-id="026ee-114">如果检测到匹配项，则接收管道将不处理交换。</span><span class="sxs-lookup"><span data-stu-id="026ee-114">If a match is detected, the receive pipeline will not process the interchange.</span></span>  
  
4. <span data-ttu-id="026ee-115">如果**交换控制编号**处于选中状态，在**检查中的重复 ISA13**字段中，输入将使用特定执行检查是否有重复交换的天数交换控制编号。</span><span class="sxs-lookup"><span data-stu-id="026ee-115">If **Interchange Control Number** is selected, in the **Check for duplicate ISA13 within** field, enter the number of days that a check for a duplicate interchange will be performed using a specific interchange control number.</span></span>  
  
5. <span data-ttu-id="026ee-116">选择**组控制编号**以阻止接收管道处理具有重复组控制编号 (GS6) 的交换。</span><span class="sxs-lookup"><span data-stu-id="026ee-116">Select **Group Control Number** to prevent the receive pipeline from processing interchanges with duplicate group control numbers (GS6).</span></span>  
  
6. <span data-ttu-id="026ee-117">选择**事务集控制编号**以阻止接收管道处理具有重复事务集控制编号 (ST2) 的交换。</span><span class="sxs-lookup"><span data-stu-id="026ee-117">Select **Transaction Set Control Number** to prevent the receive pipeline from processing interchanges with duplicate transaction set control numbers (ST2).</span></span>  
  
7. <span data-ttu-id="026ee-118">单击**Apply**以接受更改，然后才能继续进行配置，或单击**确定**以验证所做的更改，然后关闭对话框。</span><span class="sxs-lookup"><span data-stu-id="026ee-118">Click **Apply** to accept the changes before continuing with the configuration, or click **OK** to validate the changes and then close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="026ee-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="026ee-119">See Also</span></span>  
 [<span data-ttu-id="026ee-120">配置交换设置 (X12)</span><span class="sxs-lookup"><span data-stu-id="026ee-120">Configuring Interchange Settings (X12)</span></span>](../core/configuring-interchange-settings-x12.md)