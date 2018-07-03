---
title: 如何配置 SOAP 发送处理程序 |Microsoft Docs
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
ms.openlocfilehash: c4bcbe39861c37db348e1e37752fbad6d9616033
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37005478"
---
# <a name="how-to-configure-a-soap-send-handler"></a><span data-ttu-id="ba749-102">如何配置 SOAP 发送处理程序</span><span class="sxs-lookup"><span data-stu-id="ba749-102">How to Configure a SOAP Send Handler</span></span>
<span data-ttu-id="ba749-103">使用以下过程可配置 SOAP 发送处理程序。</span><span class="sxs-lookup"><span data-stu-id="ba749-103">Use the following procedure to configure the SOAP send handler.</span></span>  

> [!CAUTION]
>  <span data-ttu-id="ba749-104">在使用 HTTP 或 SOAP 适配器处理程序，建议在 Microsoft 上安装这些处理程序的主机实例[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]或[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]计算机。</span><span class="sxs-lookup"><span data-stu-id="ba749-104">When using HTTP or SOAP adapter handlers, it is recommended that you install the host instances for these handlers on Microsoft [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] or [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]computers.</span></span>  

### <a name="to-change-global-variables-for-a-soap-send-handler"></a><span data-ttu-id="ba749-105">更改 SOAP 发送处理程序的全局变量</span><span class="sxs-lookup"><span data-stu-id="ba749-105">To change global variables for a SOAP send handler</span></span>  

1. <span data-ttu-id="ba749-106">在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开[!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]**管理**，展开**BizTalk 组**，展开**平台设置**，然后展开**适配器**。</span><span class="sxs-lookup"><span data-stu-id="ba749-106">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, expand [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **Administration**, expand **BizTalk Group**, expand **Platform Settings**, and then expand **Adapters**.</span></span>  

2. <span data-ttu-id="ba749-107">在展开的适配器列表中，单击**SOAP**，在右窗格中，右键单击你想要配置，发送处理程序，再单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="ba749-107">In the expanded adapter list, click **SOAP**, in the right pane, right-click the send handler that you want to configure, and then click **Properties**.</span></span>  

3. <span data-ttu-id="ba749-108">在中**适配器处理程序属性**对话框中，在**常规**选项卡上，在**主机名**列表中，选择接收处理程序将关联的主机。</span><span class="sxs-lookup"><span data-stu-id="ba749-108">In the **Adapter Handler Properties** dialog box, on the **General** tab, in the **Host Name** list, select the host with which the receive handler will be associated.</span></span>  

4. <span data-ttu-id="ba749-109">上**代理**选项卡上，执行以下操作。</span><span class="sxs-lookup"><span data-stu-id="ba749-109">On the **Proxy** tab, do the following.</span></span>  


   |   <span data-ttu-id="ba749-110">使用此选项</span><span class="sxs-lookup"><span data-stu-id="ba749-110">Use this</span></span>    |                                                                                                                  <span data-ttu-id="ba749-111">执行的操作</span><span class="sxs-lookup"><span data-stu-id="ba749-111">To do this</span></span>                                                                                                                   |
   |---------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   | <span data-ttu-id="ba749-112">**使用代理**</span><span class="sxs-lookup"><span data-stu-id="ba749-112">**Use proxy**</span></span> |                                                                                          <span data-ttu-id="ba749-113">表示 SOAP 发送处理程序是否使用代理服务器。</span><span class="sxs-lookup"><span data-stu-id="ba749-113">Indicate whether the SOAP send handler uses a proxy server.</span></span>                                                                                          |
   |  <span data-ttu-id="ba749-114">**Server**</span><span class="sxs-lookup"><span data-stu-id="ba749-114">**Server**</span></span>   |                  <span data-ttu-id="ba749-115">指定代理服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="ba749-115">Specify the name of the proxy server.</span></span><br /><br /> <span data-ttu-id="ba749-116">此属性仅需要一个值，如果**使用代理**处于选中状态。</span><span class="sxs-lookup"><span data-stu-id="ba749-116">This property only requires a value if **Use proxy** is selected.</span></span><br /><br /> <span data-ttu-id="ba749-117">类型：字符串</span><span class="sxs-lookup"><span data-stu-id="ba749-117">Type: String</span></span><br /><br /> <span data-ttu-id="ba749-118">最小长度：0</span><span class="sxs-lookup"><span data-stu-id="ba749-118">Minimum length: 0</span></span><br /><br /> <span data-ttu-id="ba749-119">最大长度：256</span><span class="sxs-lookup"><span data-stu-id="ba749-119">Maximum length: 256</span></span>                   |
   |   <span data-ttu-id="ba749-120">**端口**</span><span class="sxs-lookup"><span data-stu-id="ba749-120">**Port**</span></span>    | <span data-ttu-id="ba749-121">指定 SOAP 发送处理程序使用的端口。</span><span class="sxs-lookup"><span data-stu-id="ba749-121">Specify the port the SOAP send handler uses.</span></span><br /><br /> <span data-ttu-id="ba749-122">此属性仅需要一个值，如果**使用代理**处于选中状态。</span><span class="sxs-lookup"><span data-stu-id="ba749-122">This property only requires a value if **Use proxy** is selected.</span></span><br /><br /> <span data-ttu-id="ba749-123">默认值：80</span><span class="sxs-lookup"><span data-stu-id="ba749-123">Default Value: 80</span></span><br /><br /> <span data-ttu-id="ba749-124">类型： Long</span><span class="sxs-lookup"><span data-stu-id="ba749-124">Type: Long</span></span><br /><br /> <span data-ttu-id="ba749-125">最小值： 0</span><span class="sxs-lookup"><span data-stu-id="ba749-125">Minimum value: 0</span></span><br /><br /> <span data-ttu-id="ba749-126">最大值： 65535</span><span class="sxs-lookup"><span data-stu-id="ba749-126">Maximum value: 65535</span></span> |
   | <span data-ttu-id="ba749-127">**用户名**</span><span class="sxs-lookup"><span data-stu-id="ba749-127">**User name**</span></span> |             <span data-ttu-id="ba749-128">指定用于身份验证的用户名。</span><span class="sxs-lookup"><span data-stu-id="ba749-128">Specify the user name to use for authentication.</span></span><br /><br /> <span data-ttu-id="ba749-129">此属性仅需要一个值，如果**使用代理**处于选中状态。</span><span class="sxs-lookup"><span data-stu-id="ba749-129">This property only requires a value if **Use proxy** is selected.</span></span><br /><br /> <span data-ttu-id="ba749-130">类型：字符串</span><span class="sxs-lookup"><span data-stu-id="ba749-130">Type: String</span></span><br /><br /> <span data-ttu-id="ba749-131">最小长度：0</span><span class="sxs-lookup"><span data-stu-id="ba749-131">Minimum length: 0</span></span><br /><br /> <span data-ttu-id="ba749-132">最大长度：256</span><span class="sxs-lookup"><span data-stu-id="ba749-132">Maximum length: 256</span></span>             |
   | <span data-ttu-id="ba749-133">**密码**</span><span class="sxs-lookup"><span data-stu-id="ba749-133">**Password**</span></span>  |             <span data-ttu-id="ba749-134">指定用于身份验证的密码。</span><span class="sxs-lookup"><span data-stu-id="ba749-134">Specify the password to use for authentication.</span></span><br /><br /> <span data-ttu-id="ba749-135">此属性仅需要一个值，如果**使用代理**处于选中状态。</span><span class="sxs-lookup"><span data-stu-id="ba749-135">This property only requires a value if **Use proxy** is selected.</span></span><br /><br /> <span data-ttu-id="ba749-136">类型：字符串</span><span class="sxs-lookup"><span data-stu-id="ba749-136">Type: String</span></span><br /><br /> <span data-ttu-id="ba749-137">最小长度：0</span><span class="sxs-lookup"><span data-stu-id="ba749-137">Minimum length: 0</span></span><br /><br /> <span data-ttu-id="ba749-138">最大长度：256</span><span class="sxs-lookup"><span data-stu-id="ba749-138">Maximum length: 256</span></span>              |


5. <span data-ttu-id="ba749-139">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="ba749-139">Click **OK**.</span></span>  

## <a name="see-also"></a><span data-ttu-id="ba749-140">请参阅</span><span class="sxs-lookup"><span data-stu-id="ba749-140">See Also</span></span>  
 <span data-ttu-id="ba749-141">[配置 SOAP 适配器](../core/configuring-the-soap-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="ba749-141">[Configuring the SOAP Adapter](../core/configuring-the-soap-adapter.md) </span></span>  
 [<span data-ttu-id="ba749-142">发布 Web 服务</span><span class="sxs-lookup"><span data-stu-id="ba749-142">Publishing Web Services</span></span>](../core/publishing-web-services.md)