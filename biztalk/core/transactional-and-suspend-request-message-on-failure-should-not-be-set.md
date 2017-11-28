---
title: "事务选项&quot;事务&quot;和错误处理选项&quot;失败的挂起请求消息&quot;应不能同时设置为 false |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cc6c66cc-6713-4396-b0d4-ac6a0e72164f
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bf8c47e364fccdb310167e56c6556423c2d4b39d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="transactions-option-quottransactionalquot-and-the-error-handling-option-quotsuspend-request-message-on-failurequot-should-not-both-be-set-to-false"></a><span data-ttu-id="519ec-102">事务选项&quot;事务&quot;和错误处理选项&quot;失败的挂起请求消息&quot;应不能同时设置为 false</span><span class="sxs-lookup"><span data-stu-id="519ec-102">Transactions option &quot;Transactional&quot; and the error handling option &quot;Suspend request message on failure&quot; should not both be set to false</span></span>
## <a name="details"></a><span data-ttu-id="519ec-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="519ec-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="519ec-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="519ec-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="519ec-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="519ec-105">Product Version</span></span>|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|<span data-ttu-id="519ec-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="519ec-106">Event ID</span></span>|<span data-ttu-id="519ec-107">0</span><span class="sxs-lookup"><span data-stu-id="519ec-107">0</span></span>|  
|<span data-ttu-id="519ec-108">事件源</span><span class="sxs-lookup"><span data-stu-id="519ec-108">Event Source</span></span>|<span data-ttu-id="519ec-109">0</span><span class="sxs-lookup"><span data-stu-id="519ec-109">0</span></span>|  
|<span data-ttu-id="519ec-110">组件</span><span class="sxs-lookup"><span data-stu-id="519ec-110">Component</span></span>|<span data-ttu-id="519ec-111">0</span><span class="sxs-lookup"><span data-stu-id="519ec-111">0</span></span>|  
|<span data-ttu-id="519ec-112">符号名称</span><span class="sxs-lookup"><span data-stu-id="519ec-112">Symbolic Name</span></span>|<span data-ttu-id="519ec-113">0</span><span class="sxs-lookup"><span data-stu-id="519ec-113">0</span></span>|  
|<span data-ttu-id="519ec-114">消息正文</span><span class="sxs-lookup"><span data-stu-id="519ec-114">Message Text</span></span>|<span data-ttu-id="519ec-115">因为消息可能会丢失，所以，事务选项“事务性”和错误处理选项“失败时挂起请求消息”不应该设置为 False。</span><span class="sxs-lookup"><span data-stu-id="519ec-115">The transactions option "Transactional" and the error handling option "Suspend request message on failure" should not both be set to false since message loss may occur.</span></span> <span data-ttu-id="519ec-116">请将其中一个或两个选项设置为 True。</span><span class="sxs-lookup"><span data-stu-id="519ec-116">Please set one or both options to true.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="519ec-117">解释</span><span class="sxs-lookup"><span data-stu-id="519ec-117">Explanation</span></span>  
 <span data-ttu-id="519ec-118">在 WCF NetMsmq 适配器选项中**事务**和**失败的挂起请求消息**应不能同时设置为 false （未选中）。</span><span class="sxs-lookup"><span data-stu-id="519ec-118">In the WCF-NetMsmq adapter, the options **Transactional** and **Suspend request message on failure** should not both be set to false (unchecked).</span></span> <span data-ttu-id="519ec-119">当消息没有被挂起并且没有存储在 MessageBox 中时，如果提交失败的消息没有作为事务回滚，则消息可能会丢失。</span><span class="sxs-lookup"><span data-stu-id="519ec-119">Message loss may occur if the failed message submission does not roll back as a transaction, while the message is not suspended and stored in the Message Box.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="519ec-120">用户操作</span><span class="sxs-lookup"><span data-stu-id="519ec-120">User Action</span></span>  
 <span data-ttu-id="519ec-121">使用以下过程验证适配器设置。</span><span class="sxs-lookup"><span data-stu-id="519ec-121">Use the following procedure to verify adapter settings.</span></span>  
  
#### <a name="to-verify-adapter-settings"></a><span data-ttu-id="519ec-122">验证适配器设置的步骤</span><span class="sxs-lookup"><span data-stu-id="519ec-122">To verify adapter settings</span></span>  
  
1.  <span data-ttu-id="519ec-123">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="519ec-123">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="519ec-124">在控制台根目录中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开**BizTalk 组**，然后展开**应用程序**。</span><span class="sxs-lookup"><span data-stu-id="519ec-124">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and expand  **Applications**.</span></span>  
  
3.  <span data-ttu-id="519ec-125">找到应用程序，然后找到您的传输。</span><span class="sxs-lookup"><span data-stu-id="519ec-125">Locate your application and then locate your transport.</span></span>  
  
4.  <span data-ttu-id="519ec-126">右键单击传输名称。</span><span class="sxs-lookup"><span data-stu-id="519ec-126">Right-click the transport name.</span></span>  
  
5.  <span data-ttu-id="519ec-127">单击 **“属性”**。</span><span class="sxs-lookup"><span data-stu-id="519ec-127">Click **Properties**.</span></span>  
  
6.  <span data-ttu-id="519ec-128">在端口**类型**列表中，选择正确的端口。</span><span class="sxs-lookup"><span data-stu-id="519ec-128">In the port **Type** list, select the correct port.</span></span>  
  
7.  <span data-ttu-id="519ec-129">单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="519ec-129">Click **Configure**.</span></span>  
  
8.  <span data-ttu-id="519ec-130">在**WCF NetMsmq 传输属性**对话框中，单击**绑定**选项卡。</span><span class="sxs-lookup"><span data-stu-id="519ec-130">In the **WCF-NetMsmq Transport Properties** dialog box, click the **Binding** tab.</span></span>  
  
9. <span data-ttu-id="519ec-131">在**事务**部分中，确定如果**事务**已选中。</span><span class="sxs-lookup"><span data-stu-id="519ec-131">In the **Transactions** section, determine if **Transactional** is checked.</span></span>  
  
10. <span data-ttu-id="519ec-132">单击**消息**选项卡。</span><span class="sxs-lookup"><span data-stu-id="519ec-132">Click the **Messages** tab.</span></span>  
  
11. <span data-ttu-id="519ec-133">确定如果**失败的挂起请求消息**已选中。</span><span class="sxs-lookup"><span data-stu-id="519ec-133">Determine if **Suspend request message on failure** is checked.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="519ec-134">这些步骤只适用于接收位置。</span><span class="sxs-lookup"><span data-stu-id="519ec-134">These steps only apply to receive locations.</span></span>