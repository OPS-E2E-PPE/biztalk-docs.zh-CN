---
title: "无效的地址 (相对 uri 需要斜杠 (&quot;-&quot;)) |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1376f924-f119-4ba8-9be1-eea7ba5f3eb6
caps.latest.revision: "22"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: aa1c43d4a86af788c67ea59c7bf0ca7dea43da39
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="invalid-address-relative-uri-needs-slash-quot-quot"></a><span data-ttu-id="c6e53-102">无效的地址 (相对 uri 需要斜杠 (&quot;-&quot;))</span><span class="sxs-lookup"><span data-stu-id="c6e53-102">Invalid address (relative uri needs slash (&quot;-&quot;))</span></span>
## <a name="details"></a><span data-ttu-id="c6e53-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="c6e53-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c6e53-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="c6e53-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="c6e53-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="c6e53-105">Product Version</span></span>|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|<span data-ttu-id="c6e53-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="c6e53-106">Event ID</span></span>|<span data-ttu-id="c6e53-107">0</span><span class="sxs-lookup"><span data-stu-id="c6e53-107">0</span></span>|  
|<span data-ttu-id="c6e53-108">事件源</span><span class="sxs-lookup"><span data-stu-id="c6e53-108">Event Source</span></span>|<span data-ttu-id="c6e53-109">0</span><span class="sxs-lookup"><span data-stu-id="c6e53-109">0</span></span>|  
|<span data-ttu-id="c6e53-110">组件</span><span class="sxs-lookup"><span data-stu-id="c6e53-110">Component</span></span>|<span data-ttu-id="c6e53-111">0</span><span class="sxs-lookup"><span data-stu-id="c6e53-111">0</span></span>|  
|<span data-ttu-id="c6e53-112">符号名称</span><span class="sxs-lookup"><span data-stu-id="c6e53-112">Symbolic Name</span></span>|<span data-ttu-id="c6e53-113">0</span><span class="sxs-lookup"><span data-stu-id="c6e53-113">0</span></span>|  
|<span data-ttu-id="c6e53-114">消息正文</span><span class="sxs-lookup"><span data-stu-id="c6e53-114">Message Text</span></span>|<span data-ttu-id="c6e53-115">地址无效；应为以斜杠（“/”）开头的相对 URI</span><span class="sxs-lookup"><span data-stu-id="c6e53-115">Invalid address; expecting relative uri starting with slash ("/")</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="c6e53-116">解释</span><span class="sxs-lookup"><span data-stu-id="c6e53-116">Explanation</span></span>  
 <span data-ttu-id="c6e53-117">您未提供一个相对地址格式正确的独立 WCF 接收位置。</span><span class="sxs-lookup"><span data-stu-id="c6e53-117">You did not provide an isolated WCF receive location with a well-formed relative address.</span></span> <span data-ttu-id="c6e53-118">例如，http://localhost/svc 不能作为相对地址使用。</span><span class="sxs-lookup"><span data-stu-id="c6e53-118">For example, http://localhost/svc will not work as a relative address.</span></span> <span data-ttu-id="c6e53-119">您不能将独立 WCF 接收位置的地址属性设置为绝对地址。</span><span class="sxs-lookup"><span data-stu-id="c6e53-119">You cannot set the Address property of the isolated WCF receive location to a absolute address.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="c6e53-120">用户操作</span><span class="sxs-lookup"><span data-stu-id="c6e53-120">User Action</span></span>  
 <span data-ttu-id="c6e53-121">使用以下过程配置地址。</span><span class="sxs-lookup"><span data-stu-id="c6e53-121">Use the following procedure to configure an address.</span></span>  
  
#### <a name="to-configure-an-address"></a><span data-ttu-id="c6e53-122">配置地址</span><span class="sxs-lookup"><span data-stu-id="c6e53-122">To configure an address</span></span>  
  
1.  <span data-ttu-id="c6e53-123">单击**启动**，单击**所有程序**，单击**Microsoft [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]** ，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="c6e53-123">Click **Start**, click **All Programs**, click **Microsoft [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]**, and click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="c6e53-124">在控制台根目录中，展开**BizTalk Server 管理**，展开**BizTalk 组**，然后展开**应用程序**。</span><span class="sxs-lookup"><span data-stu-id="c6e53-124">In the Console Root, expand  **BizTalk Server Administration**, expand **BizTalk Group**, and expand  **Applications**.</span></span>  
  
3.  <span data-ttu-id="c6e53-125">找到你的应用程序，并找到您的传输。</span><span class="sxs-lookup"><span data-stu-id="c6e53-125">Locate your application and locate your transport.</span></span>  
  
4.  <span data-ttu-id="c6e53-126">右键单击传输名称。</span><span class="sxs-lookup"><span data-stu-id="c6e53-126">Right-click the transport name.</span></span>  
  
5.  <span data-ttu-id="c6e53-127">单击 **“属性”**。</span><span class="sxs-lookup"><span data-stu-id="c6e53-127">Click **Properties**.</span></span>  
  
6.  <span data-ttu-id="c6e53-128">在端口**类型**列表中，选择正确的端口。</span><span class="sxs-lookup"><span data-stu-id="c6e53-128">In the port **Type** list, select the correct port.</span></span>  
  
7.  <span data-ttu-id="c6e53-129">单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="c6e53-129">Click **Configure**.</span></span>  
  
8.  <span data-ttu-id="c6e53-130">在**WCF [***传输类型***] 传输属性**对话框中，单击**常规**选项卡。</span><span class="sxs-lookup"><span data-stu-id="c6e53-130">In the **WCF [***transport type***] Transport Properties** dialog box, click the **General** tab.</span></span>  
  
9. <span data-ttu-id="c6e53-131">在**地址 (URI)**文本框中，更改的地址。</span><span class="sxs-lookup"><span data-stu-id="c6e53-131">In the **Address (URI)** text box, change the address.</span></span> <span data-ttu-id="c6e53-132">例如，正确格式的相对地址为 /path/service.svc。</span><span class="sxs-lookup"><span data-stu-id="c6e53-132">An example of a well-formed relative address is /path/service.svc.</span></span>  
  
 <span data-ttu-id="c6e53-133">有关接收位置的其他信息，请参阅以下内容：</span><span class="sxs-lookup"><span data-stu-id="c6e53-133">For additional information on receive locations, see the following:</span></span>  
  
-   [<span data-ttu-id="c6e53-134">如何配置 WCF CustomIsolated 接收位置</span><span class="sxs-lookup"><span data-stu-id="c6e53-134">How to Configure a WCF-CustomIsolated Receive Location</span></span>](../core/how-to-configure-a-wcf-customisolated-receive-location.md)  
  
-   [<span data-ttu-id="c6e53-135">如何配置 WCF WSHttp 接收位置</span><span class="sxs-lookup"><span data-stu-id="c6e53-135">How to Configure a WCF-WSHttp Receive Location</span></span>](../core/how-to-configure-a-wcf-wshttp-receive-location.md)  
  
-   [<span data-ttu-id="c6e53-136">如何配置 WCF BasicHttp 接收位置</span><span class="sxs-lookup"><span data-stu-id="c6e53-136">How to Configure a WCF-BasicHttp Receive Location</span></span>](http://msdn.microsoft.com/library/43f18e5d-ba28-453c-b8ce-5bcdc6f27fdd)