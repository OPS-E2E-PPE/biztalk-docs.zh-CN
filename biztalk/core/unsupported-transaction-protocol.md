---
title: 不受支持的事务处理协议 |Microsoft 文档
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
ms.openlocfilehash: 3e000c706ca438494f8b07e8ce5dba24cb4f46bd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22286885"
---
# <a name="unsupported-transaction-protocol"></a><span data-ttu-id="764f2-102">不支持的事务协议</span><span class="sxs-lookup"><span data-stu-id="764f2-102">Unsupported transaction protocol</span></span>
## <a name="details"></a><span data-ttu-id="764f2-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="764f2-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="764f2-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="764f2-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="764f2-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="764f2-105">Product Version</span></span>|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|<span data-ttu-id="764f2-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="764f2-106">Event ID</span></span>|<span data-ttu-id="764f2-107">0</span><span class="sxs-lookup"><span data-stu-id="764f2-107">0</span></span>|  
|<span data-ttu-id="764f2-108">事件源</span><span class="sxs-lookup"><span data-stu-id="764f2-108">Event Source</span></span>|<span data-ttu-id="764f2-109">0</span><span class="sxs-lookup"><span data-stu-id="764f2-109">0</span></span>|  
|<span data-ttu-id="764f2-110">组件</span><span class="sxs-lookup"><span data-stu-id="764f2-110">Component</span></span>|<span data-ttu-id="764f2-111">0</span><span class="sxs-lookup"><span data-stu-id="764f2-111">0</span></span>|  
|<span data-ttu-id="764f2-112">符号名称</span><span class="sxs-lookup"><span data-stu-id="764f2-112">Symbolic Name</span></span>|<span data-ttu-id="764f2-113">0</span><span class="sxs-lookup"><span data-stu-id="764f2-113">0</span></span>|  
|<span data-ttu-id="764f2-114">消息正文</span><span class="sxs-lookup"><span data-stu-id="764f2-114">Message Text</span></span>|<span data-ttu-id="764f2-115">不受支持的事务处理协议： {0}</span><span class="sxs-lookup"><span data-stu-id="764f2-115">Unsupported transaction protocol: {0}</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="764f2-116">解释</span><span class="sxs-lookup"><span data-stu-id="764f2-116">Explanation</span></span>  
 <span data-ttu-id="764f2-117">如果接收位置或发送端口的事务协议属性设置为无效的值，则发生此错误。</span><span class="sxs-lookup"><span data-stu-id="764f2-117">This error occurs when the transaction protocol property of a receive location or send port is set to an invalid value.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="764f2-118">用户操作</span><span class="sxs-lookup"><span data-stu-id="764f2-118">User Action</span></span>  
 <span data-ttu-id="764f2-119">若要解决此错误，请执行下列一项或多项操作:</span><span class="sxs-lookup"><span data-stu-id="764f2-119">To resolve this error, do one or more of the following:</span></span>  
  
1.  <span data-ttu-id="764f2-120">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="764f2-120">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="764f2-121">在控制台根目录中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开**BizTalk 组**，然后展开**应用程序**。</span><span class="sxs-lookup"><span data-stu-id="764f2-121">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and expand  **Applications**.</span></span>  
  
3.  <span data-ttu-id="764f2-122">找到应用程序，然后找到您的传输。</span><span class="sxs-lookup"><span data-stu-id="764f2-122">Locate your application and then locate your transport.</span></span>  
  
4.  <span data-ttu-id="764f2-123">右键单击传输名称。</span><span class="sxs-lookup"><span data-stu-id="764f2-123">Right-click the transport name.</span></span>  
  
5.  <span data-ttu-id="764f2-124">单击 **“属性”**。</span><span class="sxs-lookup"><span data-stu-id="764f2-124">Click **Properties**.</span></span>  
  
6.  <span data-ttu-id="764f2-125">在端口**类型**列表中，选择正确的端口。</span><span class="sxs-lookup"><span data-stu-id="764f2-125">In the port **Type** list, select the correct port.</span></span>  
  
7.  <span data-ttu-id="764f2-126">单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="764f2-126">Click **Configure**.</span></span>  
  
8.  <span data-ttu-id="764f2-127">在**WCF [***传输类型***] 传输属性**对话框中，单击**绑定**选项卡。</span><span class="sxs-lookup"><span data-stu-id="764f2-127">In the **WCF [***transport type***] Transport Properties** dialog box, click the **Binding** tab.</span></span>  
  
9. <span data-ttu-id="764f2-128">在**事务**部分中，选择**启用事务**选项。</span><span class="sxs-lookup"><span data-stu-id="764f2-128">In the **Transactions** section, choose the **Enable transactions** option.</span></span>  
  
10. <span data-ttu-id="764f2-129">在**事务处理协议**下拉列表中，选择**OleTransactions**或**WSAtomicTransactions**。</span><span class="sxs-lookup"><span data-stu-id="764f2-129">In the **Transactions protocol** drop-down list, choose either **OleTransactions** or **WSAtomicTransactions**.</span></span>  
  
 <span data-ttu-id="764f2-130">这些步骤仅适用于以下传输类型：</span><span class="sxs-lookup"><span data-stu-id="764f2-130">These steps only apply to the following transport types:</span></span>  
  
-   <span data-ttu-id="764f2-131">自定义</span><span class="sxs-lookup"><span data-stu-id="764f2-131">Custom</span></span>  
  
-   <span data-ttu-id="764f2-132">CustomIsolated</span><span class="sxs-lookup"><span data-stu-id="764f2-132">CustomIsolated</span></span>  
  
-   <span data-ttu-id="764f2-133">NetNamedPipe</span><span class="sxs-lookup"><span data-stu-id="764f2-133">NetNamedPipe</span></span>  
  
-   <span data-ttu-id="764f2-134">NetTcp</span><span class="sxs-lookup"><span data-stu-id="764f2-134">NetTcp</span></span>  
  
-   <span data-ttu-id="764f2-135">WShttp</span><span class="sxs-lookup"><span data-stu-id="764f2-135">WShttp</span></span>