---
title: 未知或意外的绑定元素 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 56021ff3-5abf-46ab-90bb-4531ccc9abd0
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 43c59c20968ea1329a6d689c7976aeba48650fc2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22286813"
---
# <a name="unknown-or-unexpected-binding-element"></a><span data-ttu-id="834f8-102">未知或意外的绑定元素</span><span class="sxs-lookup"><span data-stu-id="834f8-102">Unknown or unexpected binding element</span></span>
## <a name="details"></a><span data-ttu-id="834f8-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="834f8-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="834f8-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="834f8-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="834f8-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="834f8-105">Product Version</span></span>|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|<span data-ttu-id="834f8-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="834f8-106">Event ID</span></span>|<span data-ttu-id="834f8-107">0</span><span class="sxs-lookup"><span data-stu-id="834f8-107">0</span></span>|  
|<span data-ttu-id="834f8-108">事件源</span><span class="sxs-lookup"><span data-stu-id="834f8-108">Event Source</span></span>|<span data-ttu-id="834f8-109">0</span><span class="sxs-lookup"><span data-stu-id="834f8-109">0</span></span>|  
|<span data-ttu-id="834f8-110">组件</span><span class="sxs-lookup"><span data-stu-id="834f8-110">Component</span></span>|<span data-ttu-id="834f8-111">0</span><span class="sxs-lookup"><span data-stu-id="834f8-111">0</span></span>|  
|<span data-ttu-id="834f8-112">符号名称</span><span class="sxs-lookup"><span data-stu-id="834f8-112">Symbolic Name</span></span>|<span data-ttu-id="834f8-113">0</span><span class="sxs-lookup"><span data-stu-id="834f8-113">0</span></span>|  
|<span data-ttu-id="834f8-114">消息正文</span><span class="sxs-lookup"><span data-stu-id="834f8-114">Message Text</span></span>|<span data-ttu-id="834f8-115">未知或意外的绑定元素</span><span class="sxs-lookup"><span data-stu-id="834f8-115">Unknown or unexpected binding element</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="834f8-116">解释</span><span class="sxs-lookup"><span data-stu-id="834f8-116">Explanation</span></span>  
 <span data-ttu-id="834f8-117">此错误表明适配器找不到绑定中指定的用户定义的绑定元素。</span><span class="sxs-lookup"><span data-stu-id="834f8-117">This error indicates the adapter cannot find the user defined binding element specified in the binding.</span></span> <span data-ttu-id="834f8-118">这种情况主要会出现的 WCF 自定义和 WCF CustomIsolated 适配器。</span><span class="sxs-lookup"><span data-stu-id="834f8-118">This situation occurs primarily with the WCF-Custom and WCF-CustomIsolated adapters.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="834f8-119">用户操作</span><span class="sxs-lookup"><span data-stu-id="834f8-119">User Action</span></span>  
 <span data-ttu-id="834f8-120">使用以下过程验证绑定元素是否有效。</span><span class="sxs-lookup"><span data-stu-id="834f8-120">Use the following procedure to verify binding elements are valid.</span></span>  
  
#### <a name="to-verify-binding-elements-are-valid"></a><span data-ttu-id="834f8-121">验证绑定元素是否有效</span><span class="sxs-lookup"><span data-stu-id="834f8-121">To verify binding elements are valid</span></span>  
  
1.  <span data-ttu-id="834f8-122">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="834f8-122">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="834f8-123">在控制台根目录中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开**BizTalk 组**，然后展开**应用程序**。</span><span class="sxs-lookup"><span data-stu-id="834f8-123">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and expand  **Applications**.</span></span>  
  
3.  <span data-ttu-id="834f8-124">找到应用程序，然后找到您的传输。</span><span class="sxs-lookup"><span data-stu-id="834f8-124">Locate your application and then locate your transport.</span></span>  
  
4.  <span data-ttu-id="834f8-125">右键单击传输名称。</span><span class="sxs-lookup"><span data-stu-id="834f8-125">Right-click the transport name.</span></span>  
  
5.  <span data-ttu-id="834f8-126">单击 **“属性”**。</span><span class="sxs-lookup"><span data-stu-id="834f8-126">Click **Properties**.</span></span>  
  
6.  <span data-ttu-id="834f8-127">在端口**类型**列表中，选择正确的端口。</span><span class="sxs-lookup"><span data-stu-id="834f8-127">In the port **Type** list, select the correct port.</span></span>  
  
7.  <span data-ttu-id="834f8-128">单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="834f8-128">Click **Configure**.</span></span>  
  
8.  <span data-ttu-id="834f8-129">在 WCF **[***传输类型***] 传输属性**对话框中，单击**绑定**选项卡。</span><span class="sxs-lookup"><span data-stu-id="834f8-129">In the WCF **[***transport type***] Transport Properties** dialog box, click the **Binding** tab.</span></span>  
  
9. <span data-ttu-id="834f8-130">确保配置中指定的绑定元素有效。</span><span class="sxs-lookup"><span data-stu-id="834f8-130">Ensure that the binding elements specified in the configuration are valid.</span></span>