---
title: 保护发件人 ASPX 页 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- ASPX pages, protocol rules
- security, ASPX pages
- RNIFSend.aspx
- ASPX pages, security
- protocol rules [ASPX pages]
ms.assetid: 8214e3f5-a8e9-4d71-957d-ed0852035030
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0a7cf59ab1f00edeb8030681045aa6d2b512e83c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65281852"
---
# <a name="securing-the-sender-aspx-page"></a><span data-ttu-id="60abc-102">保护发件人 ASPX 页</span><span class="sxs-lookup"><span data-stu-id="60abc-102">Securing the Sender ASPX Page</span></span>
<span data-ttu-id="60abc-103">本主题介绍如何防止未经授权的使用 RNIFSend.aspx 页。</span><span class="sxs-lookup"><span data-stu-id="60abc-103">This topic describes how to protect the RNIFSend.aspx page from unauthorized use.</span></span> <span data-ttu-id="60abc-104">有两个过程，可以使用：</span><span class="sxs-lookup"><span data-stu-id="60abc-104">There are two procedures that you can use:</span></span>  
  
-   <span data-ttu-id="60abc-105">在 Internet 信息服务 (IIS) 管理器中，安全 RNIFSend.aspx 以确保任何未经授权的服务器将使用 RNIFSend.aspx 页将未经授权的消息，从你的网络传输。</span><span class="sxs-lookup"><span data-stu-id="60abc-105">In Internet Information Services (IIS) Manager, secure RNIFSend.aspx to make sure that no unauthorized server will use the RNIFSend.aspx page to transmit unauthorized messages from your network.</span></span>  
  
-   <span data-ttu-id="60abc-106">使用 Microsoft Internet Security and Acceleration (ISA) Server 创建的传出 HTTP 请求的协议规则。</span><span class="sxs-lookup"><span data-stu-id="60abc-106">Use Microsoft Internet Security and Acceleration (ISA) Server to create a protocol rule of outgoing HTTP requests.</span></span>  
  
### <a name="to-secure-rnifsendaspx"></a><span data-ttu-id="60abc-107">若要保护 RNIFSend.aspx</span><span class="sxs-lookup"><span data-stu-id="60abc-107">To secure RNIFSend.aspx</span></span>  
  
1.  <span data-ttu-id="60abc-108">在 Web 服务器上用于 RNIF 消息传输，请单击**启动**，依次指向**所有程序**，指向**管理工具**，然后单击**Internet Information Services (IIS) 管理器**。</span><span class="sxs-lookup"><span data-stu-id="60abc-108">On the Web server you use for RNIF message transmission, click **Start**, point to **All Programs**, point to **Administrative Tools**, and then click **Internet Information Services (IIS) Manager**.</span></span>  
  
2.  <span data-ttu-id="60abc-109">在 IIS 管理器中，展开本地计算机节点，展开**网站**，然后展开**Default Web Site**。</span><span class="sxs-lookup"><span data-stu-id="60abc-109">In IIS Manager, expand the local computer node, expand **Web Sites**, and then expand **Default Web Site**.</span></span>  
  
3.  <span data-ttu-id="60abc-110">单击**BTARNApp**，然后在右窗格中，右键单击**RNIFSend.aspx**。</span><span class="sxs-lookup"><span data-stu-id="60abc-110">Click **BTARNApp**, and then in the right pane, right-click **RNIFSend.aspx**.</span></span>  
  
4.  <span data-ttu-id="60abc-111">单击 **“属性”**。</span><span class="sxs-lookup"><span data-stu-id="60abc-111">Click **Properties**.</span></span> <span data-ttu-id="60abc-112">上**文件安全性**选项卡上，在**IP 地址和域名限制**部分中，单击**编辑**。</span><span class="sxs-lookup"><span data-stu-id="60abc-112">On the **File Security** tab, in the **IP address and domain name restrictions** section, click **Edit**.</span></span>  
  
5.  <span data-ttu-id="60abc-113">在 IP 地址和域名限制对话框中，单击**拒绝访问**，然后单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="60abc-113">In the IP Address and Domain Name Restrictions dialog box, click **Denied Access**, and then click **Add**.</span></span>  
  
6.  <span data-ttu-id="60abc-114">在中**授予的访问权限**对话框中，添加执行发送操作的所有 BizTalk Server。</span><span class="sxs-lookup"><span data-stu-id="60abc-114">In the **Grant Access** dialog box, add all BizTalk Servers performing send operations.</span></span> <span data-ttu-id="60abc-115">添加一台服务器，请单击**单台计算机**。</span><span class="sxs-lookup"><span data-stu-id="60abc-115">If adding a single server, click **Single computer**.</span></span> <span data-ttu-id="60abc-116">在中**IP 地址**框中，键入计算机的 IP 地址，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="60abc-116">In the **IP Address** box, type the IP address for the computer, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="60abc-117">添加一组服务器，请单击**计算机组**，然后执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="60abc-117">If adding a group of servers, click **Group of Computers**, and then do the following:</span></span>  
  
    |<span data-ttu-id="60abc-118">使用此选项</span><span class="sxs-lookup"><span data-stu-id="60abc-118">Use this</span></span>|<span data-ttu-id="60abc-119">执行的操作</span><span class="sxs-lookup"><span data-stu-id="60abc-119">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="60abc-120">**网络 ID**</span><span class="sxs-lookup"><span data-stu-id="60abc-120">**Network ID**</span></span>|<span data-ttu-id="60abc-121">键入你想要使用的网络。</span><span class="sxs-lookup"><span data-stu-id="60abc-121">Type the network you want to use.</span></span>|  
    |<span data-ttu-id="60abc-122">**子网掩码**</span><span class="sxs-lookup"><span data-stu-id="60abc-122">**Subnet mask**</span></span>|<span data-ttu-id="60abc-123">键入你想要使用的子网掩码。</span><span class="sxs-lookup"><span data-stu-id="60abc-123">Type the subnet mask you want to use.</span></span>|  
  
8.  <span data-ttu-id="60abc-124">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="60abc-124">Click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="60abc-125">如果已分离到单独的实例上运行的单独主机的所有发送操作，您只需添加此计算机。</span><span class="sxs-lookup"><span data-stu-id="60abc-125">If you have separated all your send operations to a separate host running on a separate instance, then you only have to add this computer.</span></span> <span data-ttu-id="60abc-126">您可以拒绝所有其他人访问。</span><span class="sxs-lookup"><span data-stu-id="60abc-126">You can deny all others access.</span></span>  
  
9. <span data-ttu-id="60abc-127">单击**确定**，然后单击**确定**试。</span><span class="sxs-lookup"><span data-stu-id="60abc-127">Click **OK**, and then click **OK** again.</span></span>  
  
### <a name="to-create-a-protocol-rule-of-outgoing-http-requests"></a><span data-ttu-id="60abc-128">若要创建的传出 HTTP 请求的协议规则</span><span class="sxs-lookup"><span data-stu-id="60abc-128">To create a protocol rule of outgoing HTTP requests</span></span>  
  
1.  <span data-ttu-id="60abc-129">在 ISA 管理中，单击**访问策略**，然后单击**协议规则**。</span><span class="sxs-lookup"><span data-stu-id="60abc-129">In ISA Management, click **Access Policy**, and then click **Protocol Rules**.</span></span>  
  
2.  <span data-ttu-id="60abc-130">创建一个名为的新协议规则**HTTP**使用 TCP 协议。</span><span class="sxs-lookup"><span data-stu-id="60abc-130">Create a new protocol rule named **HTTP** that uses TCP protocol.</span></span>  
  
3.  <span data-ttu-id="60abc-131">在新 HTTP 的属性页中的规则，协议**适用于**选项卡上，选择**适用于下面指定的客户端地址集**。</span><span class="sxs-lookup"><span data-stu-id="60abc-131">In the property page of your new HTTP protocol rule, in the **Applies To** tab, select **Applies to Client address sets specified below**.</span></span> <span data-ttu-id="60abc-132">输入仅这些客户端 Ip，你想要访问此页。</span><span class="sxs-lookup"><span data-stu-id="60abc-132">Enter only those client IPs that you want to access the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60abc-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="60abc-133">See Also</span></span>  
 [<span data-ttu-id="60abc-134">管理配置、证书、数据库和安全性</span><span class="sxs-lookup"><span data-stu-id="60abc-134">Manage configuration, certificates, databases, and security</span></span>](manage-configuration-certificates-databases-security.md)