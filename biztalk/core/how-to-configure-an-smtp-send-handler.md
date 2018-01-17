---
title: "如何配置一个 SMTP 发送处理程序 |Microsoft 文档"
ms.custom: 
ms.date: 2015-10-22
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- send handlers, SMTP adapters
- SMTP adapters, send handlers
- configuring [SMTP adapters], send handlers
ms.assetid: b68a36ce-f0a5-4302-a405-bb154c935f47
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 99dc71cf04d8a80b3a88630908a814957c83b8cb
ms.sourcegitcommit: 3fd1c85d9dc2ce7b77da75a5c2087cc48cfcbe50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2018
---
# <a name="how-to-configure-an-smtp-send-handler"></a><span data-ttu-id="71980-102">如何配置一个 SMTP 发送处理程序</span><span class="sxs-lookup"><span data-stu-id="71980-102">How to Configure an SMTP Send Handler</span></span>
<span data-ttu-id="71980-103">您可以在 BizTalk 管理控制台中设置 SMTP 发送处理程序属性。</span><span class="sxs-lookup"><span data-stu-id="71980-103">You can set SMTP send handler properties in the BizTalk Administration console.</span></span> <span data-ttu-id="71980-104">如果未对各 SMTP 发送端口单独设置属性，则可以将这些发送处理程序属性用作发送端口配置值。</span><span class="sxs-lookup"><span data-stu-id="71980-104">These send handler properties are used as the send port configuration values if the properties are not set on the individual SMTP send port.</span></span>  
  
### <a name="to-change-global-variables-for-an-smtp-send-handler"></a><span data-ttu-id="71980-105">更改 SMTP 发送处理程序的全局变量</span><span class="sxs-lookup"><span data-stu-id="71980-105">To change global variables for an SMTP send handler</span></span>  
  
1.  <span data-ttu-id="71980-106">在 BizTalk Server 管理控制台中，展开[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]**管理**，展开**BizTalk 组**，展开**平台设置**，然后展开**适配器**。</span><span class="sxs-lookup"><span data-stu-id="71980-106">In the BizTalk Server Administration Console, expand [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] **Administration**, expand **BizTalk Group**, expand **Platform Settings**, and then expand **Adapters**.</span></span>  
  
2.  <span data-ttu-id="71980-107">在展开的适配器列表中，单击 **SMTP**, ，而是在右窗格中，右键单击你想要配置，则发送处理程序，然后单击 **属性**。</span><span class="sxs-lookup"><span data-stu-id="71980-107">In the expanded adapter list, click **SMTP**, in the right pane, right-click the send handler that you want to configure, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="71980-108">在 **适配器处理程序属性** 对话框中，在 **常规** 选项卡上，在 **主机名** 列表中，选择的主机发送处理程序将与之相关联，并依次 **属性**。</span><span class="sxs-lookup"><span data-stu-id="71980-108">In the **Adapter Handler Properties** dialog box, on the **General** tab, in the **Host Name** list, select the host with which the send handler will be associated, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="71980-109">在 **SMTP 传输属性** 对话框中，在 **属性** 选项卡上，执行以下操作︰</span><span class="sxs-lookup"><span data-stu-id="71980-109">In the **SMTP Transport Properties** dialog box, on the **Properties** tab, do the following:</span></span>  
  
    |<span data-ttu-id="71980-110">使用此选项</span><span class="sxs-lookup"><span data-stu-id="71980-110">Use this</span></span>|<span data-ttu-id="71980-111">执行的操作</span><span class="sxs-lookup"><span data-stu-id="71980-111">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="71980-112">**SMTP 服务器名称和 TCP 端口**</span><span class="sxs-lookup"><span data-stu-id="71980-112">**SMTP server name and TCP port**</span></span>|**[!INCLUDE[bts2013r2](../includes/bts2013r2-md.md)]**<br /><br /> <span data-ttu-id="71980-113">必需的。</span><span class="sxs-lookup"><span data-stu-id="71980-113">Required.</span></span> <span data-ttu-id="71980-114">输入 SMTP 服务器名称和 （可选） 若要在发送消息时使用的 TCP 端口号。</span><span class="sxs-lookup"><span data-stu-id="71980-114">Enter the SMTP server  name and the TCP port number (optional) to use when sending messages.</span></span> <span data-ttu-id="71980-115">例如，您可以输入︰</span><span class="sxs-lookup"><span data-stu-id="71980-115">For example, you can enter:</span></span><br /><br /> <span data-ttu-id="71980-116">-mySMTPserver</span><span class="sxs-lookup"><span data-stu-id="71980-116">-   mySMTPserver</span></span><br /><span data-ttu-id="71980-117">-mySMTPserver.internet.com:2525</span><span class="sxs-lookup"><span data-stu-id="71980-117">-   mySMTPserver.internet.com:2525</span></span><br /><br /> <span data-ttu-id="71980-118">**在以前版本的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]**  （包括 BizTalk Server 2013)，只需输入 SMTP 服务器名称。</span><span class="sxs-lookup"><span data-stu-id="71980-118">**In previous versions of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]** (including BizTalk Server 2013), enter only the SMTP server name.</span></span> <span data-ttu-id="71980-119">TCP 端口 25 进行硬编码。</span><span class="sxs-lookup"><span data-stu-id="71980-119">TCP Port 25 is hard-coded.</span></span><br /><br /> <span data-ttu-id="71980-120">最大长度：256</span><span class="sxs-lookup"><span data-stu-id="71980-120">Maximum length: 256</span></span>|  
    |<span data-ttu-id="71980-121">**发件人 （电子邮件地址）**</span><span class="sxs-lookup"><span data-stu-id="71980-121">**From (e-mail address)**</span></span>|<span data-ttu-id="71980-122">必需的。</span><span class="sxs-lookup"><span data-stu-id="71980-122">Required.</span></span> <span data-ttu-id="71980-123">输入的电子邮件地址将 SMTP **从** 标头。</span><span class="sxs-lookup"><span data-stu-id="71980-123">Enter the e-mail address to put on the SMTP **From** header.</span></span><br /><br /> <span data-ttu-id="71980-124">最大长度：256</span><span class="sxs-lookup"><span data-stu-id="71980-124">Maximum length: 256</span></span>|  
    |<span data-ttu-id="71980-125">**身份验证类型**</span><span class="sxs-lookup"><span data-stu-id="71980-125">**Authentication type**</span></span>|<span data-ttu-id="71980-126">输入要使用的 SMTP 服务器的身份验证的类型。</span><span class="sxs-lookup"><span data-stu-id="71980-126">Enter the type of authentication to use with the SMTP server.</span></span><br /><br /> <span data-ttu-id="71980-127">选项：</span><span class="sxs-lookup"><span data-stu-id="71980-127">Options:</span></span><br /><br /> <span data-ttu-id="71980-128">-   **无身份验证**</span><span class="sxs-lookup"><span data-stu-id="71980-128">-   **No authentication**</span></span><br /><span data-ttu-id="71980-129">-   **基本身份验证**</span><span class="sxs-lookup"><span data-stu-id="71980-129">-   **Basic authentication**</span></span><br /><span data-ttu-id="71980-130">-   **进程帐户 (NTLM)**</span><span class="sxs-lookup"><span data-stu-id="71980-130">-   **Process account (NTLM)**</span></span><br /><br /> <span data-ttu-id="71980-131">默认值：进程帐户(NTLM)</span><span class="sxs-lookup"><span data-stu-id="71980-131">Default value: Process account (NTLM)</span></span>|  
    |<span data-ttu-id="71980-132">**用户名称**</span><span class="sxs-lookup"><span data-stu-id="71980-132">**User name**</span></span>|<span data-ttu-id="71980-133">输入要使用的 SMTP 服务器的身份验证的用户名称。</span><span class="sxs-lookup"><span data-stu-id="71980-133">Enter the user name to use for authentication with the SMTP server.</span></span><br /><br /> <span data-ttu-id="71980-134">此属性需要一个值，如果 **身份验证类型** 是 **基本身份验证**。</span><span class="sxs-lookup"><span data-stu-id="71980-134">This property requires a value if **Authentication type** is **Basic authentication**.</span></span><br /><br /> <span data-ttu-id="71980-135">最小长度：0</span><span class="sxs-lookup"><span data-stu-id="71980-135">Minimum length: 0</span></span><br /><br /> <span data-ttu-id="71980-136">最大长度：256</span><span class="sxs-lookup"><span data-stu-id="71980-136">Maximum length: 256</span></span>|  
    |<span data-ttu-id="71980-137">**密码**</span><span class="sxs-lookup"><span data-stu-id="71980-137">**Password**</span></span>|<span data-ttu-id="71980-138">输入要用于 SMTP 服务器的身份验证的密码。</span><span class="sxs-lookup"><span data-stu-id="71980-138">Enter the password to use for authentication with the SMTP server.</span></span><br /><br /> <span data-ttu-id="71980-139">此属性需要一个值，如果 **身份验证类型** 是 **基本身份验证**。</span><span class="sxs-lookup"><span data-stu-id="71980-139">This property requires a value if **Authentication type** is **Basic authentication**.</span></span><br /><br /> <span data-ttu-id="71980-140">最小长度：0</span><span class="sxs-lookup"><span data-stu-id="71980-140">Minimum length: 0</span></span><br /><br /> <span data-ttu-id="71980-141">最大长度：256</span><span class="sxs-lookup"><span data-stu-id="71980-141">Maximum length: 256</span></span>|  
  
5.  <span data-ttu-id="71980-142">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="71980-142">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71980-143">另请参阅</span><span class="sxs-lookup"><span data-stu-id="71980-143">See Also</span></span>  
 [<span data-ttu-id="71980-144">配置 SMTP 适配器</span><span class="sxs-lookup"><span data-stu-id="71980-144">Configuring the SMTP Adapter</span></span>](../core/configuring-the-smtp-adapter.md)