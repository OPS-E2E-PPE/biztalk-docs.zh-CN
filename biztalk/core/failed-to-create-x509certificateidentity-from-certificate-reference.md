---
title: 未能从证书引用创建 X509CertificateIdentity |Microsoft Docs
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
ms.openlocfilehash: b991f9acb2b5cc193d24d36e1a5de8650e7af72b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36988926"
---
# <a name="failed-to-create-x509certificateidentity-from-certificate-reference"></a><span data-ttu-id="a8b2a-102">未能从证书引用创建 X509CertificateIdentity</span><span class="sxs-lookup"><span data-stu-id="a8b2a-102">Failed to create X509CertificateIdentity from certificate reference</span></span>
## <a name="details"></a><span data-ttu-id="a8b2a-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="a8b2a-103">Details</span></span>  

|                 |                                                                                                                                            |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="a8b2a-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="a8b2a-104">Product Name</span></span>   |                             [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                             |
| <span data-ttu-id="a8b2a-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="a8b2a-105">Product Version</span></span> |                                         [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                                         |
|    <span data-ttu-id="a8b2a-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="a8b2a-106">Event ID</span></span>     |                                                                     <span data-ttu-id="a8b2a-107">0</span><span class="sxs-lookup"><span data-stu-id="a8b2a-107">0</span></span>                                                                      |
|  <span data-ttu-id="a8b2a-108">事件源</span><span class="sxs-lookup"><span data-stu-id="a8b2a-108">Event Source</span></span>   |                                                                     <span data-ttu-id="a8b2a-109">0</span><span class="sxs-lookup"><span data-stu-id="a8b2a-109">0</span></span>                                                                      |
|    <span data-ttu-id="a8b2a-110">组件</span><span class="sxs-lookup"><span data-stu-id="a8b2a-110">Component</span></span>    |                                                                     <span data-ttu-id="a8b2a-111">0</span><span class="sxs-lookup"><span data-stu-id="a8b2a-111">0</span></span>                                                                      |
|  <span data-ttu-id="a8b2a-112">符号名称</span><span class="sxs-lookup"><span data-stu-id="a8b2a-112">Symbolic Name</span></span>  |                                                                     <span data-ttu-id="a8b2a-113">0</span><span class="sxs-lookup"><span data-stu-id="a8b2a-113">0</span></span>                                                                      |
|  <span data-ttu-id="a8b2a-114">消息正文</span><span class="sxs-lookup"><span data-stu-id="a8b2a-114">Message Text</span></span>   | <span data-ttu-id="a8b2a-115">从证书引用创建 X509CertificateIdentity 时失败。</span><span class="sxs-lookup"><span data-stu-id="a8b2a-115">Failed to create X509CertificateIdentity from certificate reference.</span></span> <span data-ttu-id="a8b2a-116">(StoreName ={0}，StoreLocation ={1}，X509FindType ={2}，FindValue ="{3}")</span><span class="sxs-lookup"><span data-stu-id="a8b2a-116">(StoreName={0}, StoreLocation={1}, X509FindType={2}, FindValue="{3}")</span></span> |

## <a name="explanation"></a><span data-ttu-id="a8b2a-117">解释</span><span class="sxs-lookup"><span data-stu-id="a8b2a-117">Explanation</span></span>  
 <span data-ttu-id="a8b2a-118">此错误表示适配器创建在终结点标识配置中指定的 X509Certificate 时失败。</span><span class="sxs-lookup"><span data-stu-id="a8b2a-118">This error indicates the adapter failed to create the X509Certificate specified in the endpoint identity configuration.</span></span>  

## <a name="user-action"></a><span data-ttu-id="a8b2a-119">用户操作</span><span class="sxs-lookup"><span data-stu-id="a8b2a-119">User Action</span></span>  
 <span data-ttu-id="a8b2a-120">使用以下过程验证证书引用设置。</span><span class="sxs-lookup"><span data-stu-id="a8b2a-120">Use the following procedure to verify the certificate reference settings.</span></span>  

#### <a name="to-configure-the-certificate-reference-settings"></a><span data-ttu-id="a8b2a-121">配置证书引用设置的步骤</span><span class="sxs-lookup"><span data-stu-id="a8b2a-121">To configure the certificate reference settings</span></span>  

1. <span data-ttu-id="a8b2a-122">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="a8b2a-122">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and click **BizTalk Server Administration**.</span></span>  

2. <span data-ttu-id="a8b2a-123">在控制台根目录中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开**BizTalk 组**，然后展开**应用程序**。</span><span class="sxs-lookup"><span data-stu-id="a8b2a-123">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and expand  **Applications**.</span></span>  

3. <span data-ttu-id="a8b2a-124">找到你的应用程序，然后找到您的传输。</span><span class="sxs-lookup"><span data-stu-id="a8b2a-124">Locate your application and then locate your transport.</span></span>  

4. <span data-ttu-id="a8b2a-125">右键单击传输名称。</span><span class="sxs-lookup"><span data-stu-id="a8b2a-125">Right-click the transport name.</span></span>  

5. <span data-ttu-id="a8b2a-126">单击 **“属性”**。</span><span class="sxs-lookup"><span data-stu-id="a8b2a-126">Click **Properties**.</span></span>  

6. <span data-ttu-id="a8b2a-127">在端口**类型**列表中，选择正确的端口。</span><span class="sxs-lookup"><span data-stu-id="a8b2a-127">In the port **Type** list, select the correct port.</span></span>  

7. <span data-ttu-id="a8b2a-128">单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="a8b2a-128">Click **Configure**.</span></span>  

8. <span data-ttu-id="a8b2a-129">在中**WCF [**<em>传输类型</em>**] 传输属性**对话框中，单击**常规**选项卡。</span><span class="sxs-lookup"><span data-stu-id="a8b2a-129">In the **WCF [**<em>transport type</em>**] Transport Properties** dialog box, click the **General** tab.</span></span>  

9. <span data-ttu-id="a8b2a-130">在中**终结点标识**部分中，单击**编辑。**</span><span class="sxs-lookup"><span data-stu-id="a8b2a-130">In the **Endpoint Identity** section, click **Edit.**</span></span>  

10. <span data-ttu-id="a8b2a-131">在中**标识编辑器**对话框框中，确保**证书引用**设置是否有效。</span><span class="sxs-lookup"><span data-stu-id="a8b2a-131">In the **Identity Editor** dialog box, ensure that the **Certificate Reference** settings are valid.</span></span>
