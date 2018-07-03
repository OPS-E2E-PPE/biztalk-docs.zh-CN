---
title: 事务选项&quot;事务性&quot;和错误处理选项&quot;在失败时挂起请求消息&quot;应不能同时设置为 false |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cc6c66cc-6713-4396-b0d4-ac6a0e72164f
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3818ddba18b89aedd1185f5ad87f3682dd5686a7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36971414"
---
# <a name="transactions-option-quottransactionalquot-and-the-error-handling-option-quotsuspend-request-message-on-failurequot-should-not-both-be-set-to-false"></a><span data-ttu-id="06e46-102">事务选项&quot;事务性&quot;和错误处理选项&quot;在失败时挂起请求消息&quot;应不能同时设置为 false</span><span class="sxs-lookup"><span data-stu-id="06e46-102">Transactions option &quot;Transactional&quot; and the error handling option &quot;Suspend request message on failure&quot; should not both be set to false</span></span>
## <a name="details"></a><span data-ttu-id="06e46-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="06e46-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                                  |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="06e46-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="06e46-104">Product Name</span></span>   |                                                                [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                                |
| <span data-ttu-id="06e46-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="06e46-105">Product Version</span></span> |                                                                            [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                                                                            |
|    <span data-ttu-id="06e46-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="06e46-106">Event ID</span></span>     |                                                                                                        <span data-ttu-id="06e46-107">0</span><span class="sxs-lookup"><span data-stu-id="06e46-107">0</span></span>                                                                                                         |
|  <span data-ttu-id="06e46-108">事件源</span><span class="sxs-lookup"><span data-stu-id="06e46-108">Event Source</span></span>   |                                                                                                        <span data-ttu-id="06e46-109">0</span><span class="sxs-lookup"><span data-stu-id="06e46-109">0</span></span>                                                                                                         |
|    <span data-ttu-id="06e46-110">组件</span><span class="sxs-lookup"><span data-stu-id="06e46-110">Component</span></span>    |                                                                                                        <span data-ttu-id="06e46-111">0</span><span class="sxs-lookup"><span data-stu-id="06e46-111">0</span></span>                                                                                                         |
|  <span data-ttu-id="06e46-112">符号名称</span><span class="sxs-lookup"><span data-stu-id="06e46-112">Symbolic Name</span></span>  |                                                                                                        <span data-ttu-id="06e46-113">0</span><span class="sxs-lookup"><span data-stu-id="06e46-113">0</span></span>                                                                                                         |
|  <span data-ttu-id="06e46-114">消息正文</span><span class="sxs-lookup"><span data-stu-id="06e46-114">Message Text</span></span>   | <span data-ttu-id="06e46-115">因为消息可能会丢失，所以，事务选项“事务性”和错误处理选项“失败时挂起请求消息”不应该设置为 False。</span><span class="sxs-lookup"><span data-stu-id="06e46-115">The transactions option "Transactional" and the error handling option "Suspend request message on failure" should not both be set to false since message loss may occur.</span></span> <span data-ttu-id="06e46-116">请将其中一个或两个选项设置为 True。</span><span class="sxs-lookup"><span data-stu-id="06e46-116">Please set one or both options to true.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="06e46-117">解释</span><span class="sxs-lookup"><span data-stu-id="06e46-117">Explanation</span></span>  
 <span data-ttu-id="06e46-118">在 Wcf-netmsmq 适配器中，选项**事务性**并**在失败时挂起请求消息**应不能同时设置为 false （未选中）。</span><span class="sxs-lookup"><span data-stu-id="06e46-118">In the WCF-NetMsmq adapter, the options **Transactional** and **Suspend request message on failure** should not both be set to false (unchecked).</span></span> <span data-ttu-id="06e46-119">当消息没有被挂起并且没有存储在 MessageBox 中时，如果提交失败的消息没有作为事务回滚，则消息可能会丢失。</span><span class="sxs-lookup"><span data-stu-id="06e46-119">Message loss may occur if the failed message submission does not roll back as a transaction, while the message is not suspended and stored in the Message Box.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="06e46-120">用户操作</span><span class="sxs-lookup"><span data-stu-id="06e46-120">User Action</span></span>  
 <span data-ttu-id="06e46-121">使用以下过程验证适配器设置。</span><span class="sxs-lookup"><span data-stu-id="06e46-121">Use the following procedure to verify adapter settings.</span></span>  
  
#### <a name="to-verify-adapter-settings"></a><span data-ttu-id="06e46-122">验证适配器设置的步骤</span><span class="sxs-lookup"><span data-stu-id="06e46-122">To verify adapter settings</span></span>  
  
1. <span data-ttu-id="06e46-123">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="06e46-123">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="06e46-124">在控制台根目录中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开**BizTalk 组**，然后展开**应用程序**。</span><span class="sxs-lookup"><span data-stu-id="06e46-124">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and expand  **Applications**.</span></span>  
  
3. <span data-ttu-id="06e46-125">找到你的应用程序，然后找到您的传输。</span><span class="sxs-lookup"><span data-stu-id="06e46-125">Locate your application and then locate your transport.</span></span>  
  
4. <span data-ttu-id="06e46-126">右键单击传输名称。</span><span class="sxs-lookup"><span data-stu-id="06e46-126">Right-click the transport name.</span></span>  
  
5. <span data-ttu-id="06e46-127">单击 **“属性”**。</span><span class="sxs-lookup"><span data-stu-id="06e46-127">Click **Properties**.</span></span>  
  
6. <span data-ttu-id="06e46-128">在端口**类型**列表中，选择正确的端口。</span><span class="sxs-lookup"><span data-stu-id="06e46-128">In the port **Type** list, select the correct port.</span></span>  
  
7. <span data-ttu-id="06e46-129">单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="06e46-129">Click **Configure**.</span></span>  
  
8. <span data-ttu-id="06e46-130">在中**Wcf-netmsmq 传输属性**对话框中，单击**绑定**选项卡。</span><span class="sxs-lookup"><span data-stu-id="06e46-130">In the **WCF-NetMsmq Transport Properties** dialog box, click the **Binding** tab.</span></span>  
  
9. <span data-ttu-id="06e46-131">在中**事务**部分中，确定是否**事务性**检查。</span><span class="sxs-lookup"><span data-stu-id="06e46-131">In the **Transactions** section, determine if **Transactional** is checked.</span></span>  
  
10. <span data-ttu-id="06e46-132">单击**消息**选项卡。</span><span class="sxs-lookup"><span data-stu-id="06e46-132">Click the **Messages** tab.</span></span>  
  
11. <span data-ttu-id="06e46-133">确定是否**失败时挂起请求消息**检查。</span><span class="sxs-lookup"><span data-stu-id="06e46-133">Determine if **Suspend request message on failure** is checked.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="06e46-134">这些步骤只适用于接收位置。</span><span class="sxs-lookup"><span data-stu-id="06e46-134">These steps only apply to receive locations.</span></span>