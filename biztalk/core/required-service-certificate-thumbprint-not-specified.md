---
title: 指定必需的服务证书指纹不 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ca853667-83b5-41f2-9b54-8117b87e27d3
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ba137cd221d6cfa0ac373213d0c43dd49eafd756
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37003758"
---
# <a name="required-service-certificate-thumbprint-not-specified"></a><span data-ttu-id="e33b7-102">未指定所需的服务证书指纹</span><span class="sxs-lookup"><span data-stu-id="e33b7-102">Required service certificate thumbprint not specified</span></span>
## <a name="details"></a><span data-ttu-id="e33b7-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="e33b7-103">Details</span></span>  
  
|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  <span data-ttu-id="e33b7-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="e33b7-104">Product Name</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| <span data-ttu-id="e33b7-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="e33b7-105">Product Version</span></span> |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    <span data-ttu-id="e33b7-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="e33b7-106">Event ID</span></span>     |                                         <span data-ttu-id="e33b7-107">0</span><span class="sxs-lookup"><span data-stu-id="e33b7-107">0</span></span>                                          |
|  <span data-ttu-id="e33b7-108">事件源</span><span class="sxs-lookup"><span data-stu-id="e33b7-108">Event Source</span></span>   |                                         <span data-ttu-id="e33b7-109">0</span><span class="sxs-lookup"><span data-stu-id="e33b7-109">0</span></span>                                          |
|    <span data-ttu-id="e33b7-110">组件</span><span class="sxs-lookup"><span data-stu-id="e33b7-110">Component</span></span>    |                                         <span data-ttu-id="e33b7-111">0</span><span class="sxs-lookup"><span data-stu-id="e33b7-111">0</span></span>                                          |
|  <span data-ttu-id="e33b7-112">符号名称</span><span class="sxs-lookup"><span data-stu-id="e33b7-112">Symbolic Name</span></span>  |                                         <span data-ttu-id="e33b7-113">0</span><span class="sxs-lookup"><span data-stu-id="e33b7-113">0</span></span>                                          |
|  <span data-ttu-id="e33b7-114">消息正文</span><span class="sxs-lookup"><span data-stu-id="e33b7-114">Message Text</span></span>   |               <span data-ttu-id="e33b7-115">未指定所需的服务证书指纹</span><span class="sxs-lookup"><span data-stu-id="e33b7-115">Required service certificate thumbprint not specified</span></span>                |
  
## <a name="explanation"></a><span data-ttu-id="e33b7-116">解释</span><span class="sxs-lookup"><span data-stu-id="e33b7-116">Explanation</span></span>  
 <span data-ttu-id="e33b7-117">您没有设置 WCF 发送端口的安全设置所需的“服务证书”属性。</span><span class="sxs-lookup"><span data-stu-id="e33b7-117">You did not set the Service certificate property required for the security settings of a WCF send port.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="e33b7-118">用户操作</span><span class="sxs-lookup"><span data-stu-id="e33b7-118">User Action</span></span>  
 <span data-ttu-id="e33b7-119">使用以下过程配置“服务证书”属性。</span><span class="sxs-lookup"><span data-stu-id="e33b7-119">Use the following procedure to configure the Service certificate property.</span></span>  
  
#### <a name="to-configure-the-service-certificate-property"></a><span data-ttu-id="e33b7-120">配置服务证书属性的步骤</span><span class="sxs-lookup"><span data-stu-id="e33b7-120">To configure the Service certificate property</span></span>  
  
1. <span data-ttu-id="e33b7-121">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="e33b7-121">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="e33b7-122">在控制台根目录中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开**BizTalk 组**，然后展开**应用程序**。</span><span class="sxs-lookup"><span data-stu-id="e33b7-122">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and expand  **Applications**.</span></span>  
  
3. <span data-ttu-id="e33b7-123">找到你的应用程序，然后找到您的传输。</span><span class="sxs-lookup"><span data-stu-id="e33b7-123">Locate your application and then locate your transport.</span></span>  
  
4. <span data-ttu-id="e33b7-124">右键单击传输名称。</span><span class="sxs-lookup"><span data-stu-id="e33b7-124">Right-click the transport name.</span></span>  
  
5. <span data-ttu-id="e33b7-125">单击 **“属性”**。</span><span class="sxs-lookup"><span data-stu-id="e33b7-125">Click **Properties**.</span></span>  
  
6. <span data-ttu-id="e33b7-126">在端口**类型**列表中，选择正确的端口。</span><span class="sxs-lookup"><span data-stu-id="e33b7-126">In the port **Type** list, select the correct port.</span></span>  
  
7. <span data-ttu-id="e33b7-127">单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="e33b7-127">Click **Configure**.</span></span>  
  
8. <span data-ttu-id="e33b7-128">在中**WCF [**<em>传输类型</em>**] 传输属性**对话框中，单击**安全**选项卡。</span><span class="sxs-lookup"><span data-stu-id="e33b7-128">In the **WCF [**<em>transport type</em>**] Transport Properties** dialog box, click the **Security** tab.</span></span>  
  
9. <span data-ttu-id="e33b7-129">絋粄**服务证书**配置属性。</span><span class="sxs-lookup"><span data-stu-id="e33b7-129">Ensure that the **Service certificate** property is configured.</span></span>  
  
   <span data-ttu-id="e33b7-130">有关证书的其他信息，请参阅以下资源：</span><span class="sxs-lookup"><span data-stu-id="e33b7-130">For additional information on certificates, see the following resource:</span></span>  
  
-   [<span data-ttu-id="e33b7-131">安装用于 WCF 适配器的证书</span><span class="sxs-lookup"><span data-stu-id="e33b7-131">Installing Certificates for the WCF Adapters</span></span>](../core/installing-certificates-for-the-wcf-adapters.md)