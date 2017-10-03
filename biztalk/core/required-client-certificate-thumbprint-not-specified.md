---
title: "所需未指定的客户端证书指纹 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 19307bdb-29d7-4a79-9472-dda24dd8b263
caps.latest.revision: "21"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 17eb34655ab0acd379e493540f8cd0922e5d8be9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="required-client-certificate-thumbprint-not-specified"></a><span data-ttu-id="d9b4f-102">未指定必需的客户端证书指纹</span><span class="sxs-lookup"><span data-stu-id="d9b4f-102">Required client certificate thumbprint not specified</span></span>
## <a name="details"></a><span data-ttu-id="d9b4f-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="d9b4f-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d9b4f-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="d9b4f-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="d9b4f-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="d9b4f-105">Product Version</span></span>|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|<span data-ttu-id="d9b4f-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="d9b4f-106">Event ID</span></span>|<span data-ttu-id="d9b4f-107">0</span><span class="sxs-lookup"><span data-stu-id="d9b4f-107">0</span></span>|  
|<span data-ttu-id="d9b4f-108">事件源</span><span class="sxs-lookup"><span data-stu-id="d9b4f-108">Event Source</span></span>|<span data-ttu-id="d9b4f-109">0</span><span class="sxs-lookup"><span data-stu-id="d9b4f-109">0</span></span>|  
|<span data-ttu-id="d9b4f-110">组件</span><span class="sxs-lookup"><span data-stu-id="d9b4f-110">Component</span></span>|<span data-ttu-id="d9b4f-111">0</span><span class="sxs-lookup"><span data-stu-id="d9b4f-111">0</span></span>|  
|<span data-ttu-id="d9b4f-112">符号名称</span><span class="sxs-lookup"><span data-stu-id="d9b4f-112">Symbolic Name</span></span>|<span data-ttu-id="d9b4f-113">0</span><span class="sxs-lookup"><span data-stu-id="d9b4f-113">0</span></span>|  
|<span data-ttu-id="d9b4f-114">消息正文</span><span class="sxs-lookup"><span data-stu-id="d9b4f-114">Message Text</span></span>|<span data-ttu-id="d9b4f-115">未指定所需的客户端证书指纹。</span><span class="sxs-lookup"><span data-stu-id="d9b4f-115">Required client certificate thumbprint not specified.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="d9b4f-116">解释</span><span class="sxs-lookup"><span data-stu-id="d9b4f-116">Explanation</span></span>  
 <span data-ttu-id="d9b4f-117">您未设置 WCF 发送端口的安全设置所需的客户端证书属性。</span><span class="sxs-lookup"><span data-stu-id="d9b4f-117">You did not set the Client certificate property required for the security settings of a WCF send port.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="d9b4f-118">用户操作</span><span class="sxs-lookup"><span data-stu-id="d9b4f-118">User Action</span></span>  
 <span data-ttu-id="d9b4f-119">使用以下过程配置 WCF 发送端口的安全设置。</span><span class="sxs-lookup"><span data-stu-id="d9b4f-119">Use the following procedure to configure security settings of a WCF send port.</span></span>  
  
#### <a name="to-configure-security-settings"></a><span data-ttu-id="d9b4f-120">配置安全设置</span><span class="sxs-lookup"><span data-stu-id="d9b4f-120">To configure security settings</span></span>  
  
1.  <span data-ttu-id="d9b4f-121">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="d9b4f-121">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="d9b4f-122">在控制台根目录中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开**BizTalk 组**，然后展开**应用程序**。</span><span class="sxs-lookup"><span data-stu-id="d9b4f-122">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and expand  **Applications**.</span></span>  
  
3.  <span data-ttu-id="d9b4f-123">找到应用程序，然后找到您的传输。</span><span class="sxs-lookup"><span data-stu-id="d9b4f-123">Locate your application and then locate your transport.</span></span>  
  
4.  <span data-ttu-id="d9b4f-124">右键单击传输名称。</span><span class="sxs-lookup"><span data-stu-id="d9b4f-124">Right-click the transport name.</span></span>  
  
5.  <span data-ttu-id="d9b4f-125">单击 **“属性”**。</span><span class="sxs-lookup"><span data-stu-id="d9b4f-125">Click **Properties**.</span></span>  
  
6.  <span data-ttu-id="d9b4f-126">在端口**类型**列表中，选择正确的端口。</span><span class="sxs-lookup"><span data-stu-id="d9b4f-126">In the port **Type** list, select the correct port.</span></span>  
  
7.  <span data-ttu-id="d9b4f-127">单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="d9b4f-127">Click **Configure**.</span></span>  
  
8.  <span data-ttu-id="d9b4f-128">在**WCF [***传输类型***] 传输属性**对话框中，单击**安全**选项卡。</span><span class="sxs-lookup"><span data-stu-id="d9b4f-128">In the **WCF [***transport type***] Transport Properties** dialog box, click the **Security** tab.</span></span>  
  
9. <span data-ttu-id="d9b4f-129">确保**客户端证书**属性配置。</span><span class="sxs-lookup"><span data-stu-id="d9b4f-129">Ensure that the **Client certificate** property is configured.</span></span>  
  
 <span data-ttu-id="d9b4f-130">有关证书的其他信息，请参阅以下资源：</span><span class="sxs-lookup"><span data-stu-id="d9b4f-130">For additional information on certificates, see the following resource:</span></span>  
  
-   [<span data-ttu-id="d9b4f-131">将证书安装适用于这些 WCF 适配器</span><span class="sxs-lookup"><span data-stu-id="d9b4f-131">Installing Certificates for the WCF Adapters</span></span>](../core/installing-certificates-for-the-wcf-adapters.md)