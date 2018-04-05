---
title: PeopleSoft 传输属性对话框中 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- PeopleSoft
helpviewer_keywords:
- PeopleSoft Transport Properties dialog box
ms.assetid: 660f0a0b-e076-4f4e-8b2a-6d976acfc5ce
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 50362e60b982a2d304efea8c26f58019148e5c16
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="peoplesoft-transport-properties-dialog-box"></a><span data-ttu-id="83951-102">PeopleSoft 传输属性对话框</span><span class="sxs-lookup"><span data-stu-id="83951-102">PeopleSoft Transport Properties Dialog Box</span></span>
<span data-ttu-id="83951-103">使用 PeopleSoft 的“传输属性”对话框设置适配器所需的属性。</span><span class="sxs-lookup"><span data-stu-id="83951-103">Use the PeopleSoft Transport Properties dialog box to set the adapter-required properties.</span></span>  
  
|<span data-ttu-id="83951-104">使用此选项</span><span class="sxs-lookup"><span data-stu-id="83951-104">Use this</span></span>|<span data-ttu-id="83951-105">执行的操作</span><span class="sxs-lookup"><span data-stu-id="83951-105">To do this</span></span>|  
|--------------|----------------|  
|<span data-ttu-id="83951-106">**适配器所需的属性**</span><span class="sxs-lookup"><span data-stu-id="83951-106">**Adapter Required Properties**</span></span>||  
|<span data-ttu-id="83951-107">应用程序服务器路径</span><span class="sxs-lookup"><span data-stu-id="83951-107">Application server path</span></span>|<span data-ttu-id="83951-108">键入 PeopleSoft 服务器的路径 (例如， `//psserver.domain.com:9000`)。</span><span class="sxs-lookup"><span data-stu-id="83951-108">Type the path for the PeopleSoft server (for example, `//psserver.domain.com:9000`).</span></span>|  
|<span data-ttu-id="83951-109">JAVA_HOME</span><span class="sxs-lookup"><span data-stu-id="83951-109">JAVA_HOME</span></span>|<span data-ttu-id="83951-110">键入 JAVA_HOME 位置的名称 (例如， `<drive:>\jdk1.4.2_08`)。</span><span class="sxs-lookup"><span data-stu-id="83951-110">Type the name for the JAVA_HOME location (for example, `<drive:>\jdk1.4.2_08`).</span></span>|  
|<span data-ttu-id="83951-111">密码</span><span class="sxs-lookup"><span data-stu-id="83951-111">Password</span></span>|<span data-ttu-id="83951-112">键入此用户的密码。</span><span class="sxs-lookup"><span data-stu-id="83951-112">Type the password for this user.</span></span>|  
|<span data-ttu-id="83951-113">PeopleSoft 8.x JAR 文件</span><span class="sxs-lookup"><span data-stu-id="83951-113">PeopleSoft 8.x JAR files</span></span>|<span data-ttu-id="83951-114">键入 PeopleSoft JAR 文件的位置的路径 (例如， `<drive:>\JAR_FILES\Peoplesoft_8.4\psjoa.jar`)。</span><span class="sxs-lookup"><span data-stu-id="83951-114">Type the path for the location of the PeopleSoft JAR files (for example, `<drive:>\JAR_FILES\Peoplesoft_8.4\psjoa.jar`).</span></span>|  
|<span data-ttu-id="83951-115">用户名</span><span class="sxs-lookup"><span data-stu-id="83951-115">User name</span></span>|<span data-ttu-id="83951-116">键入用户的名称，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="83951-116">Type the name of the user, and click **OK**.</span></span>|  
|<span data-ttu-id="83951-117">**其他参数**</span><span class="sxs-lookup"><span data-stu-id="83951-117">**Additional Parameters**</span></span>||  
|<span data-ttu-id="83951-118">数据库日期格式</span><span class="sxs-lookup"><span data-stu-id="83951-118">Database Date Format</span></span>|<span data-ttu-id="83951-119">键入要在其中显示的日期的格式 (例如，**YYYY-月-日**)。</span><span class="sxs-lookup"><span data-stu-id="83951-119">Type the format in which you want dates to appear (for example,**YYYY-MM-DD**).</span></span><br /><br /> <span data-ttu-id="83951-120">日期用作键时有不同的格式。</span><span class="sxs-lookup"><span data-stu-id="83951-120">The date has a different format when used as a key.</span></span>|  
|<span data-ttu-id="83951-121">**并发控制**</span><span class="sxs-lookup"><span data-stu-id="83951-121">**Concurrency Control**</span></span>||  
|<span data-ttu-id="83951-122">最大并发调用</span><span class="sxs-lookup"><span data-stu-id="83951-122">Max Concurrent Calls</span></span>|<span data-ttu-id="83951-123">键入数字值**最大并发调用**。</span><span class="sxs-lookup"><span data-stu-id="83951-123">Type a numeric value for the **Max Concurrent Calls**.</span></span> <span data-ttu-id="83951-124">此数字表示并发调用的最大数量，例如 200。</span><span class="sxs-lookup"><span data-stu-id="83951-124">This number represents the maximum number of concurrent calls, for example, 200.</span></span><br /><br /> <span data-ttu-id="83951-125">此字段的默认值为 -1，意味着未进行任何保护。</span><span class="sxs-lookup"><span data-stu-id="83951-125">The default value for this field is -1, meaning no protection occurs.</span></span>|  
|<span data-ttu-id="83951-126">**连接**</span><span class="sxs-lookup"><span data-stu-id="83951-126">**Connection**</span></span>||  
|<span data-ttu-id="83951-127">最大会话数</span><span class="sxs-lookup"><span data-stu-id="83951-127">Maximum number of sessions</span></span>|<span data-ttu-id="83951-128">键入一个数字以表示最大会话数。</span><span class="sxs-lookup"><span data-stu-id="83951-128">Type a number to represent the maximum number of sessions.</span></span><br /><br /> <span data-ttu-id="83951-129">默认连接次数为 40。</span><span class="sxs-lookup"><span data-stu-id="83951-129">The default number of connections is 40.</span></span>|  
|<span data-ttu-id="83951-130">**刷新代理**</span><span class="sxs-lookup"><span data-stu-id="83951-130">**Refresh Agent**</span></span>||  
|<span data-ttu-id="83951-131">刷新代理</span><span class="sxs-lookup"><span data-stu-id="83951-131">Refresh Agent</span></span>|<span data-ttu-id="83951-132">选择**是**为**刷新代理**强制 runtimeagent.exe 以及要在需要时自动重新启动 browsingagent.exe 过程。</span><span class="sxs-lookup"><span data-stu-id="83951-132">Select **Yes** for the **Refresh Agent** to force the runtimeagent.exe and the browsingagent.exe processes to restart automatically when required.</span></span><br /><br /> <span data-ttu-id="83951-133">例如，您希望进程在出现以下情况时自动重新启动：丢失了与服务器的连接；或者如果向服务器中添加了内容，但是由于它没有显示在适配器向导中而无法选择它。</span><span class="sxs-lookup"><span data-stu-id="83951-133">For example, you want the process to restart automatically if it loses connection with the server, or if you add something to the server and it does not appear in the Adapter Wizard for selection.</span></span>|  
|<span data-ttu-id="83951-134">**单一登录**</span><span class="sxs-lookup"><span data-stu-id="83951-134">**Single Sign-On**</span></span>||  
|<span data-ttu-id="83951-135">关联应用程序</span><span class="sxs-lookup"><span data-stu-id="83951-135">Affiliate Application</span></span>|<span data-ttu-id="83951-136">仅当使用单一登录 (SSO) 时，才可以从列表中选择关联应用程序。</span><span class="sxs-lookup"><span data-stu-id="83951-136">Select the affiliate application from the list only if you are using Single Sign-ON (SSO).</span></span>|  
|<span data-ttu-id="83951-137">使用 SSO</span><span class="sxs-lookup"><span data-stu-id="83951-137">Use SSO</span></span>|<span data-ttu-id="83951-138">选择**是**如果你使用 SSO; 密码不需要在这种情况下。</span><span class="sxs-lookup"><span data-stu-id="83951-138">Select **Yes** if you are using SSO; a password is not required in this case.</span></span> <span data-ttu-id="83951-139">**注意：**如果你已输入了密码，并且你想要使用单一登录，右键单击密码字段，然后选择**废除密码**。</span><span class="sxs-lookup"><span data-stu-id="83951-139">**Note:**  If you already entered a password and you want to use Single Sign-On, right-click the Password field and select **Nullify Password**.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="83951-140">另请参阅</span><span class="sxs-lookup"><span data-stu-id="83951-140">See Also</span></span>  
 [<span data-ttu-id="83951-141">用于 PeopleSoft 企业的 BizTalk Adapter 的用户界面参考</span><span class="sxs-lookup"><span data-stu-id="83951-141">UI Reference for BizTalk Adapter for PeopleSoft Enterprise</span></span>](../core/ui-reference-for-biztalk-adapter-for-peoplesoft-enterprise.md)