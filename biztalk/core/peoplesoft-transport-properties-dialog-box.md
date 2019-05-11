---
title: PeopleSoft 传输属性对话框 |Microsoft Docs
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
ms.openlocfilehash: 8134f51cd6ac0ef90b2ef204b4e6c6ee38f7b6b0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65322171"
---
# <a name="peoplesoft-transport-properties-dialog-box"></a><span data-ttu-id="ae599-102">PeopleSoft 传输属性对话框</span><span class="sxs-lookup"><span data-stu-id="ae599-102">PeopleSoft Transport Properties Dialog Box</span></span>
<span data-ttu-id="ae599-103">使用 PeopleSoft 传输属性对话框设置适配器所需属性。</span><span class="sxs-lookup"><span data-stu-id="ae599-103">Use the PeopleSoft Transport Properties dialog box to set the adapter-required properties.</span></span>  
  
|<span data-ttu-id="ae599-104">使用此选项</span><span class="sxs-lookup"><span data-stu-id="ae599-104">Use this</span></span>|<span data-ttu-id="ae599-105">执行的操作</span><span class="sxs-lookup"><span data-stu-id="ae599-105">To do this</span></span>|  
|--------------|----------------|  
|<span data-ttu-id="ae599-106">**适配器必需属性**</span><span class="sxs-lookup"><span data-stu-id="ae599-106">**Adapter Required Properties**</span></span>||  
|<span data-ttu-id="ae599-107">应用程序服务器路径</span><span class="sxs-lookup"><span data-stu-id="ae599-107">Application server path</span></span>|<span data-ttu-id="ae599-108">键入 PeopleSoft 服务器的路径 (例如， `//psserver.domain.com:9000`)。</span><span class="sxs-lookup"><span data-stu-id="ae599-108">Type the path for the PeopleSoft server (for example, `//psserver.domain.com:9000`).</span></span>|  
|<span data-ttu-id="ae599-109">JAVA_HOME</span><span class="sxs-lookup"><span data-stu-id="ae599-109">JAVA_HOME</span></span>|<span data-ttu-id="ae599-110">键入 JAVA_HOME 位置的名称 (例如， `<drive:>\jdk1.4.2_08`)。</span><span class="sxs-lookup"><span data-stu-id="ae599-110">Type the name for the JAVA_HOME location (for example, `<drive:>\jdk1.4.2_08`).</span></span>|  
|<span data-ttu-id="ae599-111">Password</span><span class="sxs-lookup"><span data-stu-id="ae599-111">Password</span></span>|<span data-ttu-id="ae599-112">键入此用户的密码。</span><span class="sxs-lookup"><span data-stu-id="ae599-112">Type the password for this user.</span></span>|  
|<span data-ttu-id="ae599-113">PeopleSoft 8.x JAR 文件</span><span class="sxs-lookup"><span data-stu-id="ae599-113">PeopleSoft 8.x JAR files</span></span>|<span data-ttu-id="ae599-114">键入 PeopleSoft JAR 文件的位置的路径 (例如， `<drive:>\JAR_FILES\Peoplesoft_8.4\psjoa.jar`)。</span><span class="sxs-lookup"><span data-stu-id="ae599-114">Type the path for the location of the PeopleSoft JAR files (for example, `<drive:>\JAR_FILES\Peoplesoft_8.4\psjoa.jar`).</span></span>|  
|<span data-ttu-id="ae599-115">“用户名”</span><span class="sxs-lookup"><span data-stu-id="ae599-115">User name</span></span>|<span data-ttu-id="ae599-116">键入在用户的名称，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="ae599-116">Type the name of the user, and click **OK**.</span></span>|  
|<span data-ttu-id="ae599-117">**其他参数**</span><span class="sxs-lookup"><span data-stu-id="ae599-117">**Additional Parameters**</span></span>||  
|<span data-ttu-id="ae599-118">数据库日期格式</span><span class="sxs-lookup"><span data-stu-id="ae599-118">Database Date Format</span></span>|<span data-ttu-id="ae599-119">键入要在其中显示日期的格式 (例如，**年-月-日**)。</span><span class="sxs-lookup"><span data-stu-id="ae599-119">Type the format in which you want dates to appear (for example,**YYYY-MM-DD**).</span></span><br /><br /> <span data-ttu-id="ae599-120">日期具有不同的格式时用作键。</span><span class="sxs-lookup"><span data-stu-id="ae599-120">The date has a different format when used as a key.</span></span>|  
|<span data-ttu-id="ae599-121">**并发控制**</span><span class="sxs-lookup"><span data-stu-id="ae599-121">**Concurrency Control**</span></span>||  
|<span data-ttu-id="ae599-122">最大并发调用数</span><span class="sxs-lookup"><span data-stu-id="ae599-122">Max Concurrent Calls</span></span>|<span data-ttu-id="ae599-123">键入用于值的数值**最大并发调用**。</span><span class="sxs-lookup"><span data-stu-id="ae599-123">Type a numeric value for the **Max Concurrent Calls**.</span></span> <span data-ttu-id="ae599-124">此数字表示的最大并发调用，例如，200 数。</span><span class="sxs-lookup"><span data-stu-id="ae599-124">This number represents the maximum number of concurrent calls, for example, 200.</span></span><br /><br /> <span data-ttu-id="ae599-125">默认值为此字段为-1，这意味着无保护时发生。</span><span class="sxs-lookup"><span data-stu-id="ae599-125">The default value for this field is -1, meaning no protection occurs.</span></span>|  
|<span data-ttu-id="ae599-126">**“连接”**</span><span class="sxs-lookup"><span data-stu-id="ae599-126">**Connection**</span></span>||  
|<span data-ttu-id="ae599-127">最大会话数</span><span class="sxs-lookup"><span data-stu-id="ae599-127">Maximum number of sessions</span></span>|<span data-ttu-id="ae599-128">键入一个数字以表示最大会话数。</span><span class="sxs-lookup"><span data-stu-id="ae599-128">Type a number to represent the maximum number of sessions.</span></span><br /><br /> <span data-ttu-id="ae599-129">默认连接数为 40。</span><span class="sxs-lookup"><span data-stu-id="ae599-129">The default number of connections is 40.</span></span>|  
|<span data-ttu-id="ae599-130">**刷新代理**</span><span class="sxs-lookup"><span data-stu-id="ae599-130">**Refresh Agent**</span></span>||  
|<span data-ttu-id="ae599-131">刷新代理</span><span class="sxs-lookup"><span data-stu-id="ae599-131">Refresh Agent</span></span>|<span data-ttu-id="ae599-132">选择**是**有关**刷新代理**以强迫 runtimeagent.exe 和 browsingagent.exe 进程在需要时自动重新启动。</span><span class="sxs-lookup"><span data-stu-id="ae599-132">Select **Yes** for the **Refresh Agent** to force the runtimeagent.exe and the browsingagent.exe processes to restart automatically when required.</span></span><br /><br /> <span data-ttu-id="ae599-133">例如，您希望自动重新启动它将失去与服务器的连接，或者如果将内容添加到服务器并且不会出现在所选内容在适配器向导中的过程。</span><span class="sxs-lookup"><span data-stu-id="ae599-133">For example, you want the process to restart automatically if it loses connection with the server, or if you add something to the server and it does not appear in the Adapter Wizard for selection.</span></span>|  
|<span data-ttu-id="ae599-134">**单一登录**</span><span class="sxs-lookup"><span data-stu-id="ae599-134">**Single Sign-On**</span></span>||  
|<span data-ttu-id="ae599-135">关联应用程序</span><span class="sxs-lookup"><span data-stu-id="ae599-135">Affiliate Application</span></span>|<span data-ttu-id="ae599-136">仅当使用单一登录 (SSO)，请从列表中选择关联应用程序。</span><span class="sxs-lookup"><span data-stu-id="ae599-136">Select the affiliate application from the list only if you are using Single Sign-ON (SSO).</span></span>|  
|<span data-ttu-id="ae599-137">使用 SSO</span><span class="sxs-lookup"><span data-stu-id="ae599-137">Use SSO</span></span>|<span data-ttu-id="ae599-138">选择**是**如果您使用的 SSO; 密码则不需要在这种情况下。</span><span class="sxs-lookup"><span data-stu-id="ae599-138">Select **Yes** if you are using SSO; a password is not required in this case.</span></span> <span data-ttu-id="ae599-139">**注意：** 如果您已经输入了密码，并且你想要使用单一登录，请右键单击字段并选择的密码**置空密码**。</span><span class="sxs-lookup"><span data-stu-id="ae599-139">**Note:**  If you already entered a password and you want to use Single Sign-On, right-click the Password field and select **Nullify Password**.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ae599-140">请参阅</span><span class="sxs-lookup"><span data-stu-id="ae599-140">See Also</span></span>  
 [<span data-ttu-id="ae599-141">PeopleSoft Enterprise 的 BizTalk 适配器用户界面参考</span><span class="sxs-lookup"><span data-stu-id="ae599-141">UI Reference for BizTalk Adapter for PeopleSoft Enterprise</span></span>](../core/ui-reference-for-biztalk-adapter-for-peoplesoft-enterprise.md)