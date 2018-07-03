---
title: 从 base-64 编码的证书创建 X509CertificateIdentity 失败 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a13112bd-e0e8-4b49-ad2f-ea82b2e8162f
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 00d92c9ca3f7de567de915241d5950f5b93c06da
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36995238"
---
# <a name="failed-to-create-x509certificateidentity-from-base-64-encoded-certificate"></a><span data-ttu-id="3945b-102">从 base64 编码的证书创建 X509CertificateIdentity 失败</span><span class="sxs-lookup"><span data-stu-id="3945b-102">Failed to create X509CertificateIdentity from base-64 encoded certificate</span></span>
## <a name="details"></a><span data-ttu-id="3945b-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="3945b-103">Details</span></span>  

|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  <span data-ttu-id="3945b-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="3945b-104">Product Name</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| <span data-ttu-id="3945b-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="3945b-105">Product Version</span></span> |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    <span data-ttu-id="3945b-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="3945b-106">Event ID</span></span>     |                                         <span data-ttu-id="3945b-107">0</span><span class="sxs-lookup"><span data-stu-id="3945b-107">0</span></span>                                          |
|  <span data-ttu-id="3945b-108">事件源</span><span class="sxs-lookup"><span data-stu-id="3945b-108">Event Source</span></span>   |                                         <span data-ttu-id="3945b-109">0</span><span class="sxs-lookup"><span data-stu-id="3945b-109">0</span></span>                                          |
|    <span data-ttu-id="3945b-110">组件</span><span class="sxs-lookup"><span data-stu-id="3945b-110">Component</span></span>    |                                         <span data-ttu-id="3945b-111">0</span><span class="sxs-lookup"><span data-stu-id="3945b-111">0</span></span>                                          |
|  <span data-ttu-id="3945b-112">符号名称</span><span class="sxs-lookup"><span data-stu-id="3945b-112">Symbolic Name</span></span>  |                                         <span data-ttu-id="3945b-113">0</span><span class="sxs-lookup"><span data-stu-id="3945b-113">0</span></span>                                          |
|  <span data-ttu-id="3945b-114">消息正文</span><span class="sxs-lookup"><span data-stu-id="3945b-114">Message Text</span></span>   |     <span data-ttu-id="3945b-115">从 base64 编码的证书创建 X509CertificateIdentity 失败</span><span class="sxs-lookup"><span data-stu-id="3945b-115">Failed to create X509CertificateIdentity from base-64 encoded certificate</span></span>      |

## <a name="explanation"></a><span data-ttu-id="3945b-116">解释</span><span class="sxs-lookup"><span data-stu-id="3945b-116">Explanation</span></span>  
 <span data-ttu-id="3945b-117">此错误表示由于证书设置无效，导致适配器创建 X509Certificate 终结点标识失败。</span><span class="sxs-lookup"><span data-stu-id="3945b-117">This error indicates the adapter failed to create the X509Certificate endpoint identity because of an invalid certificate setting.</span></span>  

## <a name="user-action"></a><span data-ttu-id="3945b-118">用户操作</span><span class="sxs-lookup"><span data-stu-id="3945b-118">User Action</span></span>  
 <span data-ttu-id="3945b-119">使用以下过程配置证书。</span><span class="sxs-lookup"><span data-stu-id="3945b-119">Use the following procedure to configure certificates.</span></span>  

#### <a name="to-configure-certificates"></a><span data-ttu-id="3945b-120">配置证书的步骤</span><span class="sxs-lookup"><span data-stu-id="3945b-120">To configure certificates</span></span>  

1. <span data-ttu-id="3945b-121">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="3945b-121">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and click **BizTalk Server Administration**.</span></span>  

2. <span data-ttu-id="3945b-122">在控制台根目录中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开**BizTalk 组**，然后展开**应用程序**。</span><span class="sxs-lookup"><span data-stu-id="3945b-122">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and expand  **Applications**.</span></span>  

3. <span data-ttu-id="3945b-123">找到你的应用程序，然后找到您的传输。</span><span class="sxs-lookup"><span data-stu-id="3945b-123">Locate your application and then locate your transport.</span></span>  

4. <span data-ttu-id="3945b-124">右键单击传输名称。</span><span class="sxs-lookup"><span data-stu-id="3945b-124">Right-click the transport name.</span></span>  

5. <span data-ttu-id="3945b-125">单击 **“属性”**。</span><span class="sxs-lookup"><span data-stu-id="3945b-125">Click **Properties**.</span></span>  

6. <span data-ttu-id="3945b-126">在端口**类型**列表中，选择正确的端口。</span><span class="sxs-lookup"><span data-stu-id="3945b-126">In the port **Type** list, select the correct port.</span></span>  

7. <span data-ttu-id="3945b-127">单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="3945b-127">Click **Configure**.</span></span>  

8. <span data-ttu-id="3945b-128">在中**WCF [**<em>传输类型</em>**] 传输属性**对话框中，单击**安全**选项卡。</span><span class="sxs-lookup"><span data-stu-id="3945b-128">In the **WCF [**<em>transport type</em>**] Transport Properties** dialog box, click the **Security** tab.</span></span>  

9. <span data-ttu-id="3945b-129">确保设置正确**客户端证书指纹**并**服务证书指纹**。</span><span class="sxs-lookup"><span data-stu-id="3945b-129">Ensure that the settings are correct for the **Client Certificate Thumbprint** and the **Service Certificate Thumbprint**.</span></span>
