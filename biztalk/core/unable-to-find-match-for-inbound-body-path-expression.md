---
title: 找不到入站的正文路径表达式的匹配项 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c0382348-96c4-414c-9dda-a390d491dee8
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 69ae115eef4440490fd4fc5ed4f40c5600b6cdb2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37016970"
---
# <a name="unable-to-find-match-for-inbound-body-path-expression"></a><span data-ttu-id="8d211-102">找不到入站主体路径表达式的匹配项</span><span class="sxs-lookup"><span data-stu-id="8d211-102">Unable to find match for inbound body path expression</span></span>
## <a name="details"></a><span data-ttu-id="8d211-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="8d211-103">Details</span></span>  

|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  <span data-ttu-id="8d211-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="8d211-104">Product Name</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| <span data-ttu-id="8d211-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="8d211-105">Product Version</span></span> |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    <span data-ttu-id="8d211-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="8d211-106">Event ID</span></span>     |                                         <span data-ttu-id="8d211-107">0</span><span class="sxs-lookup"><span data-stu-id="8d211-107">0</span></span>                                          |
|  <span data-ttu-id="8d211-108">事件源</span><span class="sxs-lookup"><span data-stu-id="8d211-108">Event Source</span></span>   |                                         <span data-ttu-id="8d211-109">0</span><span class="sxs-lookup"><span data-stu-id="8d211-109">0</span></span>                                          |
|    <span data-ttu-id="8d211-110">组件</span><span class="sxs-lookup"><span data-stu-id="8d211-110">Component</span></span>    |                                         <span data-ttu-id="8d211-111">0</span><span class="sxs-lookup"><span data-stu-id="8d211-111">0</span></span>                                          |
|  <span data-ttu-id="8d211-112">符号名称</span><span class="sxs-lookup"><span data-stu-id="8d211-112">Symbolic Name</span></span>  |                                         <span data-ttu-id="8d211-113">0</span><span class="sxs-lookup"><span data-stu-id="8d211-113">0</span></span>                                          |
|  <span data-ttu-id="8d211-114">消息正文</span><span class="sxs-lookup"><span data-stu-id="8d211-114">Message Text</span></span>   |       <span data-ttu-id="8d211-115">找不到入站的正文路径表达式的匹配项"{0}"消息中</span><span class="sxs-lookup"><span data-stu-id="8d211-115">Unable to find match for inbound body path expression "{0}" in message</span></span>       |

## <a name="explanation"></a><span data-ttu-id="8d211-116">解释</span><span class="sxs-lookup"><span data-stu-id="8d211-116">Explanation</span></span>  
 <span data-ttu-id="8d211-117">对传入消息执行的正文路径表达式未返回任何匹配项。</span><span class="sxs-lookup"><span data-stu-id="8d211-117">The body path expression executed on the incoming message did not return any match.</span></span>  

## <a name="user-action"></a><span data-ttu-id="8d211-118">用户操作</span><span class="sxs-lookup"><span data-stu-id="8d211-118">User Action</span></span>  
 <span data-ttu-id="8d211-119">确保正文路径表达式正确，并且传入消息具有正确数据。</span><span class="sxs-lookup"><span data-stu-id="8d211-119">Make sure that body path expression is correct, and the incoming message has the correct data.</span></span>  

1. <span data-ttu-id="8d211-120">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="8d211-120">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and click **BizTalk Server Administration**.</span></span>  

2. <span data-ttu-id="8d211-121">在控制台根目录中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开**BizTalk 组**，然后展开**应用程序**。</span><span class="sxs-lookup"><span data-stu-id="8d211-121">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and expand  **Applications**.</span></span>  

3. <span data-ttu-id="8d211-122">找到你的应用程序，然后找到您的传输。</span><span class="sxs-lookup"><span data-stu-id="8d211-122">Locate your application and then locate your transport.</span></span>  

4. <span data-ttu-id="8d211-123">右键单击传输名称。</span><span class="sxs-lookup"><span data-stu-id="8d211-123">Right-click the transport name.</span></span>  

5. <span data-ttu-id="8d211-124">单击 **“属性”**。</span><span class="sxs-lookup"><span data-stu-id="8d211-124">Click **Properties**.</span></span>  

6. <span data-ttu-id="8d211-125">在端口**类型**列表中，选择正确的端口。</span><span class="sxs-lookup"><span data-stu-id="8d211-125">In the port **Type** list, select the correct port.</span></span>  

7. <span data-ttu-id="8d211-126">单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="8d211-126">Click **Configure**.</span></span>  

8. <span data-ttu-id="8d211-127">在 WCF **[**<em>传输类型</em>**] 传输属性**对话框中，单击**消息**选项卡。</span><span class="sxs-lookup"><span data-stu-id="8d211-127">In the WCF **[**<em>transport type</em>**] Transport Properties** dialog box, click the **Messages** tab.</span></span>  

9. <span data-ttu-id="8d211-128">在中**入站 BizTalk 消息正文**部分中，检查的信息**正文路径表达式**。</span><span class="sxs-lookup"><span data-stu-id="8d211-128">In the **Inbound BizTalk message body** section, check the information for **Body path expression**.</span></span>
