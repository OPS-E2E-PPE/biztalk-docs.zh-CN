---
title: 如何配置 SOAP 发送处理程序 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- send handlers, SOAP adapters
- SOAP adapters, denial of service
- denital of service, HTTP adapters
- configuring [SOAP adapters], send handlers
- configuring [SOAP adapters], denial of service
- SOAP adapters, send handlers
- denial of service, SOAP adapters
ms.assetid: fd610a3f-ca10-42e0-b81e-219e07e33830
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 65ca116b47e36d754b27839a09225aeb313c9e0f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22248237"
---
# <a name="how-to-configure-a-soap-send-handler"></a><span data-ttu-id="2e507-102">如何配置 SOAP 发送处理程序</span><span class="sxs-lookup"><span data-stu-id="2e507-102">How to Configure a SOAP Send Handler</span></span>
<span data-ttu-id="2e507-103">使用以下过程可配置 SOAP 发送处理程序。</span><span class="sxs-lookup"><span data-stu-id="2e507-103">Use the following procedure to configure the SOAP send handler.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="2e507-104">在使用 HTTP 或 SOAP 适配器处理程序，建议你在 Microsoft 上安装这些处理程序的主机实例[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]或[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]计算机。</span><span class="sxs-lookup"><span data-stu-id="2e507-104">When using HTTP or SOAP adapter handlers, it is recommended that you install the host instances for these handlers on Microsoft [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] or [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]computers.</span></span>  
  
### <a name="to-change-global-variables-for-a-soap-send-handler"></a><span data-ttu-id="2e507-105">更改 SOAP 发送处理程序的全局变量</span><span class="sxs-lookup"><span data-stu-id="2e507-105">To change global variables for a SOAP send handler</span></span>  
  
1.  <span data-ttu-id="2e507-106">在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开[!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]**管理**，展开**BizTalk 组**，展开**平台设置**，然后展开**适配器**。</span><span class="sxs-lookup"><span data-stu-id="2e507-106">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, expand [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **Administration**, expand **BizTalk Group**, expand **Platform Settings**, and then expand **Adapters**.</span></span>  
  
2.  <span data-ttu-id="2e507-107">在展开的适配器列表中，单击**SOAP**，而是在右窗格中，右键单击你想要配置，则发送处理程序，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="2e507-107">In the expanded adapter list, click **SOAP**, in the right pane, right-click the send handler that you want to configure, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="2e507-108">在**适配器处理程序属性**对话框中，在**常规**选项卡上，在**主机名**列表中，选择接收处理程序将与之关联的主机。</span><span class="sxs-lookup"><span data-stu-id="2e507-108">In the **Adapter Handler Properties** dialog box, on the **General** tab, in the **Host Name** list, select the host with which the receive handler will be associated.</span></span>  
  
4.  <span data-ttu-id="2e507-109">上**代理**选项卡上，执行以下操作。</span><span class="sxs-lookup"><span data-stu-id="2e507-109">On the **Proxy** tab, do the following.</span></span>  
  
    |<span data-ttu-id="2e507-110">使用此选项</span><span class="sxs-lookup"><span data-stu-id="2e507-110">Use this</span></span>|<span data-ttu-id="2e507-111">执行的操作</span><span class="sxs-lookup"><span data-stu-id="2e507-111">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="2e507-112">**使用代理**</span><span class="sxs-lookup"><span data-stu-id="2e507-112">**Use proxy**</span></span>|<span data-ttu-id="2e507-113">表示 SOAP 发送处理程序是否使用代理服务器。</span><span class="sxs-lookup"><span data-stu-id="2e507-113">Indicate whether the SOAP send handler uses a proxy server.</span></span>|  
    |<span data-ttu-id="2e507-114">**Server**</span><span class="sxs-lookup"><span data-stu-id="2e507-114">**Server**</span></span>|<span data-ttu-id="2e507-115">指定代理服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="2e507-115">Specify the name of the proxy server.</span></span><br /><br /> <span data-ttu-id="2e507-116">此属性仅需要一个值，如果**使用代理**选择。</span><span class="sxs-lookup"><span data-stu-id="2e507-116">This property only requires a value if **Use proxy** is selected.</span></span><br /><br /> <span data-ttu-id="2e507-117">类型：字符串</span><span class="sxs-lookup"><span data-stu-id="2e507-117">Type: String</span></span><br /><br /> <span data-ttu-id="2e507-118">最小长度：0</span><span class="sxs-lookup"><span data-stu-id="2e507-118">Minimum length: 0</span></span><br /><br /> <span data-ttu-id="2e507-119">最大长度：256</span><span class="sxs-lookup"><span data-stu-id="2e507-119">Maximum length: 256</span></span>|  
    |<span data-ttu-id="2e507-120">**端口**</span><span class="sxs-lookup"><span data-stu-id="2e507-120">**Port**</span></span>|<span data-ttu-id="2e507-121">指定 SOAP 发送处理程序使用的端口。</span><span class="sxs-lookup"><span data-stu-id="2e507-121">Specify the port the SOAP send handler uses.</span></span><br /><br /> <span data-ttu-id="2e507-122">此属性仅需要一个值，如果**使用代理**选择。</span><span class="sxs-lookup"><span data-stu-id="2e507-122">This property only requires a value if **Use proxy** is selected.</span></span><br /><br /> <span data-ttu-id="2e507-123">默认值：80</span><span class="sxs-lookup"><span data-stu-id="2e507-123">Default Value: 80</span></span><br /><br /> <span data-ttu-id="2e507-124">类型： 长</span><span class="sxs-lookup"><span data-stu-id="2e507-124">Type: Long</span></span><br /><br /> <span data-ttu-id="2e507-125">最小值： 0</span><span class="sxs-lookup"><span data-stu-id="2e507-125">Minimum value: 0</span></span><br /><br /> <span data-ttu-id="2e507-126">最大值： 65535</span><span class="sxs-lookup"><span data-stu-id="2e507-126">Maximum value: 65535</span></span>|  
    |<span data-ttu-id="2e507-127">**用户名**</span><span class="sxs-lookup"><span data-stu-id="2e507-127">**User name**</span></span>|<span data-ttu-id="2e507-128">指定用于身份验证的用户名。</span><span class="sxs-lookup"><span data-stu-id="2e507-128">Specify the user name to use for authentication.</span></span><br /><br /> <span data-ttu-id="2e507-129">此属性仅需要一个值，如果**使用代理**选择。</span><span class="sxs-lookup"><span data-stu-id="2e507-129">This property only requires a value if **Use proxy** is selected.</span></span><br /><br /> <span data-ttu-id="2e507-130">类型：字符串</span><span class="sxs-lookup"><span data-stu-id="2e507-130">Type: String</span></span><br /><br /> <span data-ttu-id="2e507-131">最小长度：0</span><span class="sxs-lookup"><span data-stu-id="2e507-131">Minimum length: 0</span></span><br /><br /> <span data-ttu-id="2e507-132">最大长度：256</span><span class="sxs-lookup"><span data-stu-id="2e507-132">Maximum length: 256</span></span>|  
    |<span data-ttu-id="2e507-133">**密码**</span><span class="sxs-lookup"><span data-stu-id="2e507-133">**Password**</span></span>|<span data-ttu-id="2e507-134">指定用于身份验证的密码。</span><span class="sxs-lookup"><span data-stu-id="2e507-134">Specify the password to use for authentication.</span></span><br /><br /> <span data-ttu-id="2e507-135">此属性仅需要一个值，如果**使用代理**选择。</span><span class="sxs-lookup"><span data-stu-id="2e507-135">This property only requires a value if **Use proxy** is selected.</span></span><br /><br /> <span data-ttu-id="2e507-136">类型：字符串</span><span class="sxs-lookup"><span data-stu-id="2e507-136">Type: String</span></span><br /><br /> <span data-ttu-id="2e507-137">最小长度：0</span><span class="sxs-lookup"><span data-stu-id="2e507-137">Minimum length: 0</span></span><br /><br /> <span data-ttu-id="2e507-138">最大长度：256</span><span class="sxs-lookup"><span data-stu-id="2e507-138">Maximum length: 256</span></span>|  
  
5.  <span data-ttu-id="2e507-139">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="2e507-139">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e507-140">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2e507-140">See Also</span></span>  
 <span data-ttu-id="2e507-141">[配置 SOAP 适配器](../core/configuring-the-soap-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="2e507-141">[Configuring the SOAP Adapter](../core/configuring-the-soap-adapter.md) </span></span>  
 [<span data-ttu-id="2e507-142">发布 Web 服务</span><span class="sxs-lookup"><span data-stu-id="2e507-142">Publishing Web Services</span></span>](../core/publishing-web-services.md)