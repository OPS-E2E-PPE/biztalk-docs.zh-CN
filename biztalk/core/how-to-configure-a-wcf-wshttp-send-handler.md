---
title: "如何配置 WCF WSHttp 发送处理程序 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WCF-WSHttp adapters, global variables
- configuring [WCF-WSHttp adapters], send handlers
- configuring [WCF-WSHttp adapters], global variables
- send handlers, WCF-WSHttp adapters
ms.assetid: b2c30edb-8f7b-4d3c-812b-5b877c47fda1
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 11566bcc902ccbda33b6b15922292390df3d5201
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-a-wcf-wshttp-send-handler"></a><span data-ttu-id="7a044-102">如何配置 WCF-WSHttp 发送处理程序</span><span class="sxs-lookup"><span data-stu-id="7a044-102">How to Configure a WCF-WSHttp Send Handler</span></span>
<span data-ttu-id="7a044-103">使用以下过程可配置 WCF-WSHttp 发送处理程序。</span><span class="sxs-lookup"><span data-stu-id="7a044-103">Use the following procedure to configure the WCF-WSHttp send handler.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="7a044-104">使用 WCF-WSHttp 适配器处理程序时，建议在 [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] 或 [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] 计算机上安装这些处理程序的主机实例。</span><span class="sxs-lookup"><span data-stu-id="7a044-104">When using WCF-WSHttp adapter handlers, it is recommended that you install the host instances for these handlers on [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] or [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] computers.</span></span>  
  
### <a name="to-change-global-variables-for-a-wcf-wshttp-send-handler"></a><span data-ttu-id="7a044-105">更改 WCF-WSHttp 发送处理程序的全局变量</span><span class="sxs-lookup"><span data-stu-id="7a044-105">To change global variables for a WCF-WSHttp send handler</span></span>  
  
1.  <span data-ttu-id="7a044-106">在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开[!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]**管理**，展开**BizTalk 组**，展开**平台设置**，然后展开**适配器**。</span><span class="sxs-lookup"><span data-stu-id="7a044-106">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, expand [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **Administration**, expand **BizTalk Group**, expand **Platform Settings**, and then expand **Adapters**.</span></span>  
  
2.  <span data-ttu-id="7a044-107">在展开的适配器列表中，单击**WCF WSHttp**，而是在右窗格中，右键单击你想要配置，则发送处理程序，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="7a044-107">In the expanded adapter list, click **WCF-WSHttp**, in the right pane, right-click the send handler that you want to configure, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="7a044-108">在**适配器处理程序属性**对话框中，在**常规**选项卡上，在**主机名**列表中，选择接收处理程序将与之关联的主机。</span><span class="sxs-lookup"><span data-stu-id="7a044-108">In the **Adapter Handler Properties** dialog box, on the **General** tab, in the **Host Name** list, select the host with which the receive handler will be associated.</span></span>  
  
4.  <span data-ttu-id="7a044-109">在**常规**选项卡上，单击**属性**上**代理**选项卡上，执行以下操作。</span><span class="sxs-lookup"><span data-stu-id="7a044-109">In the **General** tab, Click **Properties**, On the **Proxy** tab, do the following.</span></span>  
  
    |<span data-ttu-id="7a044-110">使用此选项</span><span class="sxs-lookup"><span data-stu-id="7a044-110">Use this</span></span>|<span data-ttu-id="7a044-111">执行的操作</span><span class="sxs-lookup"><span data-stu-id="7a044-111">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="7a044-112">**使用代理**</span><span class="sxs-lookup"><span data-stu-id="7a044-112">**Use proxy**</span></span>|<span data-ttu-id="7a044-113">指示此发送端口是否使用代理服务器。</span><span class="sxs-lookup"><span data-stu-id="7a044-113">Indicate whether this send port uses a proxy server.</span></span><br /><br /> <span data-ttu-id="7a044-114">默认值为清除此复选框。</span><span class="sxs-lookup"><span data-stu-id="7a044-114">The default value is cleared.</span></span>|  
    |<span data-ttu-id="7a044-115">**Address**</span><span class="sxs-lookup"><span data-stu-id="7a044-115">**Address**</span></span>|<span data-ttu-id="7a044-116">指定代理服务器的地址。</span><span class="sxs-lookup"><span data-stu-id="7a044-116">Specify the address of the proxy server.</span></span> <span data-ttu-id="7a044-117">使用**https**或**http**根据安全配置的方案。</span><span class="sxs-lookup"><span data-stu-id="7a044-117">Use the **https** or the **http** scheme depending on the security configuration.</span></span> <span data-ttu-id="7a044-118">此地址后面可跟冒号和端口号。</span><span class="sxs-lookup"><span data-stu-id="7a044-118">This address can be followed by a colon and the port number.</span></span> <span data-ttu-id="7a044-119">例如， http://127.0.0.1:8080.</span><span class="sxs-lookup"><span data-stu-id="7a044-119">For example, http://127.0.0.1:8080.</span></span><br /><br /> <span data-ttu-id="7a044-120">此属性，则需要值才**使用代理**选择。</span><span class="sxs-lookup"><span data-stu-id="7a044-120">This property requires a value only if **Use proxy** is selected.</span></span><br /><br /> <span data-ttu-id="7a044-121">类型：字符串</span><span class="sxs-lookup"><span data-stu-id="7a044-121">Type: String</span></span><br /><br /> <span data-ttu-id="7a044-122">最大长度：256</span><span class="sxs-lookup"><span data-stu-id="7a044-122">Maximum length: 256</span></span><br /><br /> <span data-ttu-id="7a044-123">默认值为空字符串。</span><span class="sxs-lookup"><span data-stu-id="7a044-123">The default is an empty string.</span></span>|  
    |<span data-ttu-id="7a044-124">**用户名**</span><span class="sxs-lookup"><span data-stu-id="7a044-124">**User name**</span></span>|<span data-ttu-id="7a044-125">指定用于身份验证的用户名。</span><span class="sxs-lookup"><span data-stu-id="7a044-125">Specify the user name to use for authentication.</span></span> <span data-ttu-id="7a044-126">如果使用集成或基本验证，则用户名将包括域，即采用“域\用户名”格式。</span><span class="sxs-lookup"><span data-stu-id="7a044-126">If integrated or Basic authentication is used, the user name includes the domain, that is, domain\username.</span></span> <span data-ttu-id="7a044-127">如果使用摘要式身份验证，则用户名不包括域\\。</span><span class="sxs-lookup"><span data-stu-id="7a044-127">If Digest authentication is used, the user name does not include domain\\.</span></span><br /><br /> <span data-ttu-id="7a044-128">此属性，则需要值才**使用代理**选择。</span><span class="sxs-lookup"><span data-stu-id="7a044-128">This property requires a value only if **Use proxy** is selected.</span></span><br /><br /> <span data-ttu-id="7a044-129">类型：字符串</span><span class="sxs-lookup"><span data-stu-id="7a044-129">Type: String</span></span><br /><br /> <span data-ttu-id="7a044-130">最小长度：0</span><span class="sxs-lookup"><span data-stu-id="7a044-130">Minimum length: 0</span></span><br /><br /> <span data-ttu-id="7a044-131">最大长度：256</span><span class="sxs-lookup"><span data-stu-id="7a044-131">Maximum length: 256</span></span><br /><br /> <span data-ttu-id="7a044-132">默认值为空字符串。</span><span class="sxs-lookup"><span data-stu-id="7a044-132">The default is an empty string.</span></span>|  
    |<span data-ttu-id="7a044-133">**密码**</span><span class="sxs-lookup"><span data-stu-id="7a044-133">**Password**</span></span>|<span data-ttu-id="7a044-134">指定用于身份验证的密码。</span><span class="sxs-lookup"><span data-stu-id="7a044-134">Specify the password to use for authentication.</span></span><br /><br /> <span data-ttu-id="7a044-135">此属性，则需要值才**使用代理**选择。</span><span class="sxs-lookup"><span data-stu-id="7a044-135">This property requires a value only if **Use proxy** is selected.</span></span><br /><br /> <span data-ttu-id="7a044-136">类型：字符串</span><span class="sxs-lookup"><span data-stu-id="7a044-136">Type: String</span></span><br /><br /> <span data-ttu-id="7a044-137">最小长度：0</span><span class="sxs-lookup"><span data-stu-id="7a044-137">Minimum length: 0</span></span><br /><br /> <span data-ttu-id="7a044-138">最大长度：256</span><span class="sxs-lookup"><span data-stu-id="7a044-138">Maximum length: 256</span></span><br /><br /> <span data-ttu-id="7a044-139">默认值为空字符串。</span><span class="sxs-lookup"><span data-stu-id="7a044-139">The default is an empty string.</span></span>|  
  
5.  <span data-ttu-id="7a044-140">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="7a044-140">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a044-141">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7a044-141">See Also</span></span>  
 [<span data-ttu-id="7a044-142">配置 WCF WSHttp 适配器</span><span class="sxs-lookup"><span data-stu-id="7a044-142">Configuring the WCF-WSHttp Adapter</span></span>](../core/configuring-the-wcf-wshttp-adapter.md)