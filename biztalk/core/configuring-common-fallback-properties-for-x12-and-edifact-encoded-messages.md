---
title: "配置常见回退属性的 X12 和 EDIFACT 编码消息 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7393d6ac-b901-43ef-a8d6-c5b0b3033257
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5b99d6e60a2a5955a9f0873156dbc5f822b3d519
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
---
# <a name="configuring-common-fallback-properties-for-x12-and-edifact-encoded-messages"></a><span data-ttu-id="6bceb-102">为 X12 和 EDIFACT 编码的消息配置通用后备属性</span><span class="sxs-lookup"><span data-stu-id="6bceb-102">Configuring Common Fallback Properties for X12 and EDIFACT Encoded Messages</span></span>
<span data-ttu-id="6bceb-103">后备属性同时适用于 X12（包括 HIPAA）和 EDIFACT 编码的交换。</span><span class="sxs-lookup"><span data-stu-id="6bceb-103">Fallback properties apply to both X12 (including HIPAA) - and EDIFACT-encoded interchanges.</span></span> <span data-ttu-id="6bceb-104">和所有后备协议属性一样，仅当 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 尚未确定解析传入或传出消息所用的协议时，这些属性才适用。</span><span class="sxs-lookup"><span data-stu-id="6bceb-104">As with all fallback agreement properties, these properties apply only when [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] has not determined the agreement to which an incoming our outgoing message resolves to.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="6bceb-105">先决条件</span><span class="sxs-lookup"><span data-stu-id="6bceb-105">Prerequisites</span></span>  
 <span data-ttu-id="6bceb-106">必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组或 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators 组成员的身份登录。</span><span class="sxs-lookup"><span data-stu-id="6bceb-106">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-set-common-global-properties"></a><span data-ttu-id="6bceb-107">设置公用全局属性</span><span class="sxs-lookup"><span data-stu-id="6bceb-107">To set common global properties</span></span>  
  
1.  <span data-ttu-id="6bceb-108">在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**方**节点，，然后单击**X12 回退设置**或**EDIFACT 回退设置**。</span><span class="sxs-lookup"><span data-stu-id="6bceb-108">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, right-click the **Parties** node, and then click **X12 Fallback Settings** or **EDIFACT Fallback Settings**.</span></span>  
  
2.  <span data-ttu-id="6bceb-109">在**回退设置常规页**选项卡上，在**常规**页上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="6bceb-109">In the **Fallback Settings General Pages** tab, on the **General** page, do the following:</span></span>  
  
    1.  <span data-ttu-id="6bceb-110">单击**启用回退设置**启用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]使用回退协议设置，如果没有协议已解决的传入或传出消息。</span><span class="sxs-lookup"><span data-stu-id="6bceb-110">Click **Enable Fallback Settings** to enable [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to use the fallback agreement settings if no agreement is resolved for incoming or outgoing messages.</span></span>  
  
        > [!IMPORTANT]
        >  <span data-ttu-id="6bceb-111">如果未选中该选项，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 将不使用后备协议中的属性集。</span><span class="sxs-lookup"><span data-stu-id="6bceb-111">If this option is not checked, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will not use the properties set in the fallback agreement.</span></span>  
  
    2.  <span data-ttu-id="6bceb-112">单击**激活 EDI 报告**激活报告的所有 EDI 消息。</span><span class="sxs-lookup"><span data-stu-id="6bceb-112">Click **Activate EDI Reporting** to activate reporting for all EDI messages.</span></span> <span data-ttu-id="6bceb-113">这可确保消息均显示在状态报告功能，通过单击底部的链接可显示的屏幕**组中心数据库**BizTalk Server 管理控制台窗格。</span><span class="sxs-lookup"><span data-stu-id="6bceb-113">This ensures messages are displayed in the status reporting screens displayed by clicking the links at the bottom of the **Group Hub** pane of the BizTalk Server Administration Console.</span></span>  
  
    3.  <span data-ttu-id="6bceb-114">如果你单击**激活 EDI 报告**，单击**存储事务的一组负载，可用于报告**存储事务设置中的跟踪 (BizTalkDTADb) 数据库的 EDI 表。</span><span class="sxs-lookup"><span data-stu-id="6bceb-114">If you clicked **Activate EDI Reporting**, click **Store transaction set/payload for reporting** to store transaction sets in the EDI tables of the tracking (BizTalkDTADb) database.</span></span>  
  
    4.  <span data-ttu-id="6bceb-115">单击**日志 EDI 错误和警告由 EDI 引擎到 Windows 事件日志生成**记录错误/警告消息由 EDI 引擎 （EDI 管道，批处理业务流程，路由业务流程，等等），生成的上下文向 Windows 事件查看器的信息。</span><span class="sxs-lookup"><span data-stu-id="6bceb-115">Click **Log EDI errors and warnings generated by EDI engine to Windows event log** to log error/warnings messages generated by the EDI engine (EDI pipelines, batching orchestration, routing orchestration, etc.), with contextual information, to the Windows Event Viewer.</span></span> <span data-ttu-id="6bceb-116">如果清除此项，则这些错误/警告消息将不会记录到事件查看器中。</span><span class="sxs-lookup"><span data-stu-id="6bceb-116">If cleared, these error/warning messages will not be logged to the Event Viewer.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="6bceb-117">无论是否选中此复选框，系统/处理错误都会记录到事件查看器中。</span><span class="sxs-lookup"><span data-stu-id="6bceb-117">System/processing errors are logged in the Event Viewer whether or not this checkbox is selected.</span></span>  
  
3.  <span data-ttu-id="6bceb-118">单击**应用**接受所做的更改，然后才能继续进行配置，或单击**确定**若要验证并接受所做的更改，然后关闭对话框。</span><span class="sxs-lookup"><span data-stu-id="6bceb-118">Click **Apply** to accept the changes before continuing with the configuration, or click **OK** to validate and accept the changes and then close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6bceb-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6bceb-119">See Also</span></span>  
 [<span data-ttu-id="6bceb-120">配置全局或后备协议属性</span><span class="sxs-lookup"><span data-stu-id="6bceb-120">Configuring Global or Fallback Agreement Properties</span></span>](../core/configuring-global-or-fallback-agreement-properties.md)