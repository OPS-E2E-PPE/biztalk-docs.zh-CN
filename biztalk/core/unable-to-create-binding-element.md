---
title: 无法创建绑定元素 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5b036833-12ba-463c-8df6-9d5e1ac26b6d
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 117ad9a604f0b0d61cd494da52d84b8aabd4a9eb
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36987894"
---
# <a name="unable-to-create-binding-element"></a><span data-ttu-id="f9079-102">无法创建绑定元素</span><span class="sxs-lookup"><span data-stu-id="f9079-102">Unable to create binding element</span></span>
## <a name="details"></a><span data-ttu-id="f9079-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="f9079-103">Details</span></span>  

|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  <span data-ttu-id="f9079-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="f9079-104">Product Name</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| <span data-ttu-id="f9079-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="f9079-105">Product Version</span></span> |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    <span data-ttu-id="f9079-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="f9079-106">Event ID</span></span>     |                                         <span data-ttu-id="f9079-107">0</span><span class="sxs-lookup"><span data-stu-id="f9079-107">0</span></span>                                          |
|  <span data-ttu-id="f9079-108">事件源</span><span class="sxs-lookup"><span data-stu-id="f9079-108">Event Source</span></span>   |                                         <span data-ttu-id="f9079-109">0</span><span class="sxs-lookup"><span data-stu-id="f9079-109">0</span></span>                                          |
|    <span data-ttu-id="f9079-110">组件</span><span class="sxs-lookup"><span data-stu-id="f9079-110">Component</span></span>    |                                         <span data-ttu-id="f9079-111">0</span><span class="sxs-lookup"><span data-stu-id="f9079-111">0</span></span>                                          |
|  <span data-ttu-id="f9079-112">符号名称</span><span class="sxs-lookup"><span data-stu-id="f9079-112">Symbolic Name</span></span>  |                                         <span data-ttu-id="f9079-113">0</span><span class="sxs-lookup"><span data-stu-id="f9079-113">0</span></span>                                          |
|  <span data-ttu-id="f9079-114">消息正文</span><span class="sxs-lookup"><span data-stu-id="f9079-114">Message Text</span></span>   |                 <span data-ttu-id="f9079-115">无法创建绑定的绑定元素"{0}</span><span class="sxs-lookup"><span data-stu-id="f9079-115">Unable to create binding element for binding "{0}</span></span>                  |

## <a name="explanation"></a><span data-ttu-id="f9079-116">解释</span><span class="sxs-lookup"><span data-stu-id="f9079-116">Explanation</span></span>  
 <span data-ttu-id="f9079-117">此错误表明适配器无法创建运行时配置中指定的绑定。</span><span class="sxs-lookup"><span data-stu-id="f9079-117">This error indicates the adapter cannot create the binding specified in the configuration at runtime.</span></span> <span data-ttu-id="f9079-118">主要与 Wcf-custom 和 Wcf-customisolated 适配器出现这种情况。</span><span class="sxs-lookup"><span data-stu-id="f9079-118">This situation occurs primarily with the WCF-Custom and WCF-CustomIsolated adapters.</span></span>  

## <a name="user-action"></a><span data-ttu-id="f9079-119">用户操作</span><span class="sxs-lookup"><span data-stu-id="f9079-119">User Action</span></span>  
 <span data-ttu-id="f9079-120">使用以下过程验证绑定元素是否有效。</span><span class="sxs-lookup"><span data-stu-id="f9079-120">Use the following procedure to verify binding elements are valid.</span></span>  

#### <a name="to-verify-binding-elements"></a><span data-ttu-id="f9079-121">若要验证绑定元素</span><span class="sxs-lookup"><span data-stu-id="f9079-121">To verify binding elements</span></span>  

1. <span data-ttu-id="f9079-122">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="f9079-122">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and click **BizTalk Server Administration**.</span></span>  

2. <span data-ttu-id="f9079-123">在控制台根目录中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开**BizTalk 组**，然后展开**应用程序**。</span><span class="sxs-lookup"><span data-stu-id="f9079-123">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and expand  **Applications**.</span></span>  

3. <span data-ttu-id="f9079-124">找到你的应用程序，然后找到您的传输。</span><span class="sxs-lookup"><span data-stu-id="f9079-124">Locate your application and then locate your transport.</span></span>  

4. <span data-ttu-id="f9079-125">右键单击传输名称。</span><span class="sxs-lookup"><span data-stu-id="f9079-125">Right-click the transport name.</span></span>  

5. <span data-ttu-id="f9079-126">单击 **“属性”**。</span><span class="sxs-lookup"><span data-stu-id="f9079-126">Click **Properties**.</span></span>  

6. <span data-ttu-id="f9079-127">在端口**类型**列表中，选择正确的端口。</span><span class="sxs-lookup"><span data-stu-id="f9079-127">In the port **Type** list, select the correct port.</span></span>  

7. <span data-ttu-id="f9079-128">单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="f9079-128">Click **Configure**.</span></span>  

8. <span data-ttu-id="f9079-129">在中**WCF [**<em>传输类型</em>**] 传输属性**对话框中，单击**绑定**选项卡。</span><span class="sxs-lookup"><span data-stu-id="f9079-129">In the **WCF [**<em>transport type</em>**] Transport Properties** dialog box, click the **Binding** tab.</span></span>  

9. <span data-ttu-id="f9079-130">确保配置中指定的绑定元素有效。</span><span class="sxs-lookup"><span data-stu-id="f9079-130">Ensure that the binding elements specified in the configuration are valid.</span></span>
