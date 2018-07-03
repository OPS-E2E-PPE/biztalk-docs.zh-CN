---
title: 找不到入站的主体路径表达式的内容 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ed294662-a94e-4fbb-b125-878a27107eab
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c9de18c9d3fa7ccf89a33eb6b09e6c11381a73a2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36972022"
---
# <a name="unable-to-find-content-for-inbound-body-path-expression"></a><span data-ttu-id="71ff0-102">找不到入站的主体路径表达式的内容</span><span class="sxs-lookup"><span data-stu-id="71ff0-102">Unable to find content for inbound body path expression</span></span>
## <a name="details"></a><span data-ttu-id="71ff0-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="71ff0-103">Details</span></span>  

|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  <span data-ttu-id="71ff0-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="71ff0-104">Product Name</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| <span data-ttu-id="71ff0-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="71ff0-105">Product Version</span></span> |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    <span data-ttu-id="71ff0-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="71ff0-106">Event ID</span></span>     |                                         <span data-ttu-id="71ff0-107">0</span><span class="sxs-lookup"><span data-stu-id="71ff0-107">0</span></span>                                          |
|  <span data-ttu-id="71ff0-108">事件源</span><span class="sxs-lookup"><span data-stu-id="71ff0-108">Event Source</span></span>   |                                         <span data-ttu-id="71ff0-109">0</span><span class="sxs-lookup"><span data-stu-id="71ff0-109">0</span></span>                                          |
|    <span data-ttu-id="71ff0-110">组件</span><span class="sxs-lookup"><span data-stu-id="71ff0-110">Component</span></span>    |                                         <span data-ttu-id="71ff0-111">0</span><span class="sxs-lookup"><span data-stu-id="71ff0-111">0</span></span>                                          |
|  <span data-ttu-id="71ff0-112">符号名称</span><span class="sxs-lookup"><span data-stu-id="71ff0-112">Symbolic Name</span></span>  |                                         <span data-ttu-id="71ff0-113">0</span><span class="sxs-lookup"><span data-stu-id="71ff0-113">0</span></span>                                          |
|  <span data-ttu-id="71ff0-114">消息正文</span><span class="sxs-lookup"><span data-stu-id="71ff0-114">Message Text</span></span>   |      <span data-ttu-id="71ff0-115">找不到内容的入站的正文路径表达式"{0}"消息中</span><span class="sxs-lookup"><span data-stu-id="71ff0-115">Unable to find content for inbound body path expression "{0}" in message</span></span>      |

## <a name="explanation"></a><span data-ttu-id="71ff0-116">解释</span><span class="sxs-lookup"><span data-stu-id="71ff0-116">Explanation</span></span>  
 <span data-ttu-id="71ff0-117">通过执行正文路径表达式从传入消息中提取的内容不包含任何数据。</span><span class="sxs-lookup"><span data-stu-id="71ff0-117">The content extracted from the incoming message by executing the body path expression does not contain any data.</span></span>  

## <a name="user-action"></a><span data-ttu-id="71ff0-118">用户操作</span><span class="sxs-lookup"><span data-stu-id="71ff0-118">User Action</span></span>  
 <span data-ttu-id="71ff0-119">确保正文路径表达式正确，并且传入消息具有正确数据。</span><span class="sxs-lookup"><span data-stu-id="71ff0-119">Make sure that body path expression is correct, and the incoming message has the correct data.</span></span>  

1. <span data-ttu-id="71ff0-120">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="71ff0-120">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and click **BizTalk Server Administration**.</span></span>  

2. <span data-ttu-id="71ff0-121">在控制台根目录中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开**BizTalk 组**，然后展开**应用程序**。</span><span class="sxs-lookup"><span data-stu-id="71ff0-121">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and expand  **Applications**.</span></span>  

3. <span data-ttu-id="71ff0-122">找到你的应用程序，然后找到您的传输。</span><span class="sxs-lookup"><span data-stu-id="71ff0-122">Locate your application and then locate your transport.</span></span>  

4. <span data-ttu-id="71ff0-123">右键单击传输名称。</span><span class="sxs-lookup"><span data-stu-id="71ff0-123">Right-click the transport name.</span></span>  

5. <span data-ttu-id="71ff0-124">单击 **“属性”**。</span><span class="sxs-lookup"><span data-stu-id="71ff0-124">Click **Properties**.</span></span>  

6. <span data-ttu-id="71ff0-125">在端口**类型**列表中，选择正确的端口。</span><span class="sxs-lookup"><span data-stu-id="71ff0-125">In the port **Type** list, select the correct port.</span></span>  

7. <span data-ttu-id="71ff0-126">单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="71ff0-126">Click **Configure**.</span></span>  

8. <span data-ttu-id="71ff0-127">在 WCF **[**<em>传输类型</em>**] 传输属性**对话框中，单击**消息**选项卡。</span><span class="sxs-lookup"><span data-stu-id="71ff0-127">In the WCF **[**<em>transport type</em>**] Transport Properties** dialog box, click the **Messages** tab.</span></span>  

9. <span data-ttu-id="71ff0-128">在中**入站 BizTalk 消息正文**部分中，检查的信息**正文路径表达式**。</span><span class="sxs-lookup"><span data-stu-id="71ff0-128">In the **Inbound BizTalk message body** section, check the information for **Body path expression**.</span></span>
