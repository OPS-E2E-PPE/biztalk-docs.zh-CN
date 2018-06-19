---
title: 未能从证书引用创建 X509CertificateIdentity |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a3acee8e-c035-4e58-8bfc-397885b4d185
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4c6bb03698010d667b27334f17fa7270de845c68
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22246061"
---
# <a name="failed-to-create-x509certificateidentity-from-certificate-reference"></a><span data-ttu-id="ef4ba-102">未能从证书引用创建 X509CertificateIdentity</span><span class="sxs-lookup"><span data-stu-id="ef4ba-102">Failed to create X509CertificateIdentity from certificate reference</span></span>
## <a name="details"></a><span data-ttu-id="ef4ba-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="ef4ba-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ef4ba-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="ef4ba-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="ef4ba-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="ef4ba-105">Product Version</span></span>|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|<span data-ttu-id="ef4ba-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="ef4ba-106">Event ID</span></span>|<span data-ttu-id="ef4ba-107">0</span><span class="sxs-lookup"><span data-stu-id="ef4ba-107">0</span></span>|  
|<span data-ttu-id="ef4ba-108">事件源</span><span class="sxs-lookup"><span data-stu-id="ef4ba-108">Event Source</span></span>|<span data-ttu-id="ef4ba-109">0</span><span class="sxs-lookup"><span data-stu-id="ef4ba-109">0</span></span>|  
|<span data-ttu-id="ef4ba-110">组件</span><span class="sxs-lookup"><span data-stu-id="ef4ba-110">Component</span></span>|<span data-ttu-id="ef4ba-111">0</span><span class="sxs-lookup"><span data-stu-id="ef4ba-111">0</span></span>|  
|<span data-ttu-id="ef4ba-112">符号名称</span><span class="sxs-lookup"><span data-stu-id="ef4ba-112">Symbolic Name</span></span>|<span data-ttu-id="ef4ba-113">0</span><span class="sxs-lookup"><span data-stu-id="ef4ba-113">0</span></span>|  
|<span data-ttu-id="ef4ba-114">消息正文</span><span class="sxs-lookup"><span data-stu-id="ef4ba-114">Message Text</span></span>|<span data-ttu-id="ef4ba-115">从证书引用创建 X509CertificateIdentity 时失败。</span><span class="sxs-lookup"><span data-stu-id="ef4ba-115">Failed to create X509CertificateIdentity from certificate reference.</span></span> <span data-ttu-id="ef4ba-116">(StoreName = {0}，StoreLocation = \ {1 \}，X509FindType = \ {2 \}，FindValue ="\ {3\}")</span><span class="sxs-lookup"><span data-stu-id="ef4ba-116">(StoreName={0}, StoreLocation={1}, X509FindType={2}, FindValue="{3}")</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="ef4ba-117">解释</span><span class="sxs-lookup"><span data-stu-id="ef4ba-117">Explanation</span></span>  
 <span data-ttu-id="ef4ba-118">此错误表示适配器创建在终结点标识配置中指定的 X509Certificate 时失败。</span><span class="sxs-lookup"><span data-stu-id="ef4ba-118">This error indicates the adapter failed to create the X509Certificate specified in the endpoint identity configuration.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="ef4ba-119">用户操作</span><span class="sxs-lookup"><span data-stu-id="ef4ba-119">User Action</span></span>  
 <span data-ttu-id="ef4ba-120">使用以下过程验证证书引用设置。</span><span class="sxs-lookup"><span data-stu-id="ef4ba-120">Use the following procedure to verify the certificate reference settings.</span></span>  
  
#### <a name="to-configure-the-certificate-reference-settings"></a><span data-ttu-id="ef4ba-121">配置证书引用设置的步骤</span><span class="sxs-lookup"><span data-stu-id="ef4ba-121">To configure the certificate reference settings</span></span>  
  
1.  <span data-ttu-id="ef4ba-122">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="ef4ba-122">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="ef4ba-123">在控制台根目录中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开**BizTalk 组**，然后展开**应用程序**。</span><span class="sxs-lookup"><span data-stu-id="ef4ba-123">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and expand  **Applications**.</span></span>  
  
3.  <span data-ttu-id="ef4ba-124">找到应用程序，然后找到您的传输。</span><span class="sxs-lookup"><span data-stu-id="ef4ba-124">Locate your application and then locate your transport.</span></span>  
  
4.  <span data-ttu-id="ef4ba-125">右键单击传输名称。</span><span class="sxs-lookup"><span data-stu-id="ef4ba-125">Right-click the transport name.</span></span>  
  
5.  <span data-ttu-id="ef4ba-126">单击 **“属性”**。</span><span class="sxs-lookup"><span data-stu-id="ef4ba-126">Click **Properties**.</span></span>  
  
6.  <span data-ttu-id="ef4ba-127">在端口**类型**列表中，选择正确的端口。</span><span class="sxs-lookup"><span data-stu-id="ef4ba-127">In the port **Type** list, select the correct port.</span></span>  
  
7.  <span data-ttu-id="ef4ba-128">单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="ef4ba-128">Click **Configure**.</span></span>  
  
8.  <span data-ttu-id="ef4ba-129">在**WCF [***传输类型***] 传输属性**对话框中，单击**常规**选项卡。</span><span class="sxs-lookup"><span data-stu-id="ef4ba-129">In the **WCF [***transport type***] Transport Properties** dialog box, click the **General** tab.</span></span>  
  
9. <span data-ttu-id="ef4ba-130">在**终结点标识**部分中，单击**编辑。**</span><span class="sxs-lookup"><span data-stu-id="ef4ba-130">In the **Endpoint Identity** section, click **Edit.**</span></span>  
  
10. <span data-ttu-id="ef4ba-131">在**标识编辑器**对话框框中，确保**证书引用**设置都是有效。</span><span class="sxs-lookup"><span data-stu-id="ef4ba-131">In the **Identity Editor** dialog box, ensure that the **Certificate Reference** settings are valid.</span></span>