---
title: WCF 客户端必须允许模拟才能使用单一登录 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b5b9f294-4d8a-4a12-91e8-8d325db7c420
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a2d5ebfc9853f10417c1d2ad2c41a0d2531ff6de
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36971470"
---
# <a name="wcf-client-must-allow-impersonation-to-use-single-sign-on"></a><span data-ttu-id="61701-102">WCF 客户端必须允许模拟才能使用单一登录</span><span class="sxs-lookup"><span data-stu-id="61701-102">WCF client must allow impersonation to use Single Sign-On</span></span>
## <a name="details"></a><span data-ttu-id="61701-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="61701-103">Details</span></span>  

|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  <span data-ttu-id="61701-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="61701-104">Product Name</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| <span data-ttu-id="61701-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="61701-105">Product Version</span></span> |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    <span data-ttu-id="61701-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="61701-106">Event ID</span></span>     |                                         <span data-ttu-id="61701-107">0</span><span class="sxs-lookup"><span data-stu-id="61701-107">0</span></span>                                          |
|  <span data-ttu-id="61701-108">事件源</span><span class="sxs-lookup"><span data-stu-id="61701-108">Event Source</span></span>   |                                         <span data-ttu-id="61701-109">0</span><span class="sxs-lookup"><span data-stu-id="61701-109">0</span></span>                                          |
|    <span data-ttu-id="61701-110">组件</span><span class="sxs-lookup"><span data-stu-id="61701-110">Component</span></span>    |                                         <span data-ttu-id="61701-111">0</span><span class="sxs-lookup"><span data-stu-id="61701-111">0</span></span>                                          |
|  <span data-ttu-id="61701-112">符号名称</span><span class="sxs-lookup"><span data-stu-id="61701-112">Symbolic Name</span></span>  |                                         <span data-ttu-id="61701-113">0</span><span class="sxs-lookup"><span data-stu-id="61701-113">0</span></span>                                          |
|  <span data-ttu-id="61701-114">消息正文</span><span class="sxs-lookup"><span data-stu-id="61701-114">Message Text</span></span>   |           <span data-ttu-id="61701-115">WCF 客户端必须允许模拟使用单一登录。</span><span class="sxs-lookup"><span data-stu-id="61701-115">The WCF client must allow impersonation to use Single Sign-On</span></span>            |

## <a name="explanation"></a><span data-ttu-id="61701-116">解释</span><span class="sxs-lookup"><span data-stu-id="61701-116">Explanation</span></span>  
 <span data-ttu-id="61701-117">在接收位置启用了单一登录 (SSO)，但 WCF 客户端不允许模拟。</span><span class="sxs-lookup"><span data-stu-id="61701-117">Single Sign-On (SSO) is enabled in the receive location but the WCF client does not allow impersonation.</span></span>  

## <a name="user-action"></a><span data-ttu-id="61701-118">用户操作</span><span class="sxs-lookup"><span data-stu-id="61701-118">User Action</span></span>  
 <span data-ttu-id="61701-119">确保调用服务的 WCF 客户端允许模拟。</span><span class="sxs-lookup"><span data-stu-id="61701-119">Ensure that the WCF client invoking the service allows impersonation.</span></span>  

1. <span data-ttu-id="61701-120">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="61701-120">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and click **BizTalk Server Administration**.</span></span>  

2. <span data-ttu-id="61701-121">在控制台根目录中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开**BizTalk 组**，然后展开**应用程序**。</span><span class="sxs-lookup"><span data-stu-id="61701-121">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and expand  **Applications**.</span></span>  

3. <span data-ttu-id="61701-122">找到你的应用程序，然后找到您的传输。</span><span class="sxs-lookup"><span data-stu-id="61701-122">Locate your application and then locate your transport.</span></span>  

4. <span data-ttu-id="61701-123">右键单击传输名称。</span><span class="sxs-lookup"><span data-stu-id="61701-123">Right-click the transport name.</span></span>  

5. <span data-ttu-id="61701-124">单击 **“属性”**。</span><span class="sxs-lookup"><span data-stu-id="61701-124">Click **Properties**.</span></span>  

6. <span data-ttu-id="61701-125">在端口**类型**列表中，选择**WCF 自定义**(或**Wcf-customisolate**)。</span><span class="sxs-lookup"><span data-stu-id="61701-125">In the port **Type** list, select **WCF-Custom** (or **WCF-CustomIsolate**).</span></span>  

7. <span data-ttu-id="61701-126">单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="61701-126">Click **Configure**.</span></span>  

8. <span data-ttu-id="61701-127">在中**WCF [**<em>传输类型</em>**] 传输属性**对话框中，单击**行为**选项卡。</span><span class="sxs-lookup"><span data-stu-id="61701-127">In the **WCF [**<em>transport type</em>**] Transport Properties** dialog box, click the **Behavior** tab.</span></span>  

9. <span data-ttu-id="61701-128">在中**行为**部分中，单击**ServiceAuthorization**。</span><span class="sxs-lookup"><span data-stu-id="61701-128">In the **Behavior** section, click **ServiceAuthorization**.</span></span> <span data-ttu-id="61701-129">在中**配置**部分中，该属性**ImpersonateCallerForAllOperations**应设置为**True**。</span><span class="sxs-lookup"><span data-stu-id="61701-129">In the **Configuration** section, the property **ImpersonateCallerForAllOperations** should be set to **True**.</span></span>  

10. <span data-ttu-id="61701-130">在中**WCF [**<em>传输类型</em>**] 传输属性**对话框中，单击**其他**选项卡。</span><span class="sxs-lookup"><span data-stu-id="61701-130">In the **WCF [**<em>transport type</em>**] Transport Properties** dialog box, click the **Other** tab.</span></span>  

11. <span data-ttu-id="61701-131">在凭据部分中，选择相应选项**使用单一登录**。</span><span class="sxs-lookup"><span data-stu-id="61701-131">In the Credentials sections, select the option **Use Single Sign-On**.</span></span>
