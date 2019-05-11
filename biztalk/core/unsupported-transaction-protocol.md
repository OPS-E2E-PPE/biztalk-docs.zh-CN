---
title: 不支持事务协议 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 11fb2497-9971-4e85-b21a-161734f071e0
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 05023ca937ab8ff74323f4dbcbe52643e5efa01d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399465"
---
# <a name="unsupported-transaction-protocol"></a><span data-ttu-id="edaf0-102">不支持的事务协议</span><span class="sxs-lookup"><span data-stu-id="edaf0-102">Unsupported transaction protocol</span></span>
## <a name="details"></a><span data-ttu-id="edaf0-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="edaf0-103">Details</span></span>  
  
|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  <span data-ttu-id="edaf0-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="edaf0-104">Product Name</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| <span data-ttu-id="edaf0-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="edaf0-105">Product Version</span></span> |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    <span data-ttu-id="edaf0-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="edaf0-106">Event ID</span></span>     |                                         <span data-ttu-id="edaf0-107">0</span><span class="sxs-lookup"><span data-stu-id="edaf0-107">0</span></span>                                          |
|  <span data-ttu-id="edaf0-108">事件源</span><span class="sxs-lookup"><span data-stu-id="edaf0-108">Event Source</span></span>   |                                         <span data-ttu-id="edaf0-109">0</span><span class="sxs-lookup"><span data-stu-id="edaf0-109">0</span></span>                                          |
|    <span data-ttu-id="edaf0-110">组件</span><span class="sxs-lookup"><span data-stu-id="edaf0-110">Component</span></span>    |                                         <span data-ttu-id="edaf0-111">0</span><span class="sxs-lookup"><span data-stu-id="edaf0-111">0</span></span>                                          |
|  <span data-ttu-id="edaf0-112">符号名称</span><span class="sxs-lookup"><span data-stu-id="edaf0-112">Symbolic Name</span></span>  |                                         <span data-ttu-id="edaf0-113">0</span><span class="sxs-lookup"><span data-stu-id="edaf0-113">0</span></span>                                          |
|  <span data-ttu-id="edaf0-114">消息正文</span><span class="sxs-lookup"><span data-stu-id="edaf0-114">Message Text</span></span>   |                       <span data-ttu-id="edaf0-115">不支持的事务协议： {0}</span><span class="sxs-lookup"><span data-stu-id="edaf0-115">Unsupported transaction protocol: {0}</span></span>                        |
  
## <a name="explanation"></a><span data-ttu-id="edaf0-116">解释</span><span class="sxs-lookup"><span data-stu-id="edaf0-116">Explanation</span></span>  
 <span data-ttu-id="edaf0-117">当接收位置或发送端口的事务协议属性设置为无效值时，将发生此错误。</span><span class="sxs-lookup"><span data-stu-id="edaf0-117">This error occurs when the transaction protocol property of a receive location or send port is set to an invalid value.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="edaf0-118">用户操作</span><span class="sxs-lookup"><span data-stu-id="edaf0-118">User Action</span></span>  
 <span data-ttu-id="edaf0-119">若要解决此错误，请执行下列一项或多项操作:</span><span class="sxs-lookup"><span data-stu-id="edaf0-119">To resolve this error, do one or more of the following:</span></span>  
  
1. <span data-ttu-id="edaf0-120">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="edaf0-120">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="edaf0-121">在控制台根目录中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开**BizTalk 组**，然后展开**应用程序**。</span><span class="sxs-lookup"><span data-stu-id="edaf0-121">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and expand  **Applications**.</span></span>  
  
3. <span data-ttu-id="edaf0-122">找到你的应用程序，然后找到您的传输。</span><span class="sxs-lookup"><span data-stu-id="edaf0-122">Locate your application and then locate your transport.</span></span>  
  
4. <span data-ttu-id="edaf0-123">右键单击传输名称。</span><span class="sxs-lookup"><span data-stu-id="edaf0-123">Right-click the transport name.</span></span>  
  
5. <span data-ttu-id="edaf0-124">单击 **“属性”**。</span><span class="sxs-lookup"><span data-stu-id="edaf0-124">Click **Properties**.</span></span>  
  
6. <span data-ttu-id="edaf0-125">在端口**类型**列表中，选择正确的端口。</span><span class="sxs-lookup"><span data-stu-id="edaf0-125">In the port **Type** list, select the correct port.</span></span>  
  
7. <span data-ttu-id="edaf0-126">单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="edaf0-126">Click **Configure**.</span></span>  
  
8. <span data-ttu-id="edaf0-127">在中**WCF [**<em>传输类型</em>**] 传输属性**对话框中，单击**绑定**选项卡。</span><span class="sxs-lookup"><span data-stu-id="edaf0-127">In the **WCF [**<em>transport type</em>**] Transport Properties** dialog box, click the **Binding** tab.</span></span>  
  
9. <span data-ttu-id="edaf0-128">在中**事务**部分中，选择**启用事务**选项。</span><span class="sxs-lookup"><span data-stu-id="edaf0-128">In the **Transactions** section, choose the **Enable transactions** option.</span></span>  
  
10. <span data-ttu-id="edaf0-129">在中**事务处理协议**下拉列表中，选择**OleTransactions**或**WSAtomicTransactions**。</span><span class="sxs-lookup"><span data-stu-id="edaf0-129">In the **Transactions protocol** drop-down list, choose either **OleTransactions** or **WSAtomicTransactions**.</span></span>  
  
    <span data-ttu-id="edaf0-130">这些步骤仅适用于以下传输类型：</span><span class="sxs-lookup"><span data-stu-id="edaf0-130">These steps only apply to the following transport types:</span></span>  
  
-   <span data-ttu-id="edaf0-131">自定义</span><span class="sxs-lookup"><span data-stu-id="edaf0-131">Custom</span></span>  
  
-   <span data-ttu-id="edaf0-132">CustomIsolated</span><span class="sxs-lookup"><span data-stu-id="edaf0-132">CustomIsolated</span></span>  
  
-   <span data-ttu-id="edaf0-133">NetNamedPipe</span><span class="sxs-lookup"><span data-stu-id="edaf0-133">NetNamedPipe</span></span>  
  
-   <span data-ttu-id="edaf0-134">NetTcp</span><span class="sxs-lookup"><span data-stu-id="edaf0-134">NetTcp</span></span>  
  
-   <span data-ttu-id="edaf0-135">WShttp</span><span class="sxs-lookup"><span data-stu-id="edaf0-135">WShttp</span></span>